## apn.Provider([options])

A provider represents a new connection to the [APNs Provider API][provider-api].

Options:

 - `token` {Object} Configuration for Provider Authentication Tokens. (Defaults to: `null` i.e. fallback to Certificates)
     - `token.key` {Buffer|String} The filename of the provider token key (as supplied by Apple) to load from disk, or a Buffer/String containing the key data.
     - `token.keyId` {String} The ID of the key issued by Apple
     - `token.teamId` {String} ID of the team associated with the provider token key

 - `cert` {Buffer|String} The filename of the connection certificate to load from disk, or a Buffer/String containing the certificate data. (Defaults to: `cert.pem`)

 - `key` {Buffer|String} The filename of the connection key to load from disk, or a Buffer/String containing the key data. (Defaults to: `key.pem`)

 - `ca` An array of trusted certificates. Each element should contain either a filename to load, or a Buffer/String (in PEM format) to be used directly. If this is omitted several well known "root" CAs will be used. - You may need to use this as some environments don't include the CA used by Apple (entrust_2048)

 - `pfx` {Buffer|String} File path for private key, certificate and CA certs in PFX or PKCS12 format, or a Buffer containing the PFX data. If supplied will always be used instead of certificate and key above

 - `passphrase` {String} The passphrase for the connection key, if required

 - `production` {Boolean} Specifies which environment to connect to: Production (if true) or Sandbox - The hostname will be set automatically. (Defaults to NODE_ENV == "production", i.e. false unless the NODE_ENV environment variable is set accordingly)

 - `rejectUnauthorized` {Boolean} Reject Unauthorized property to be passed through to tls.connect() (Defaults to `true`)

 - `address` {String} The address of the APNs server to send notifications to. If not provided, will connect to standard APNs server

- `port` {Number} The port of the APNs server to send notifications to. (Defaults to 443)

 - `manageChannelsAddress` {String} The address of the APNs channel management server to send notifications to. If not provided, will connect to standard APNs channel management server

 - `manageChannelsPort` {Number} The port of the APNs channel management server to send notifications to. If not provided, will connect to standard APNs channel management port

 - `proxy` {host: String, port: Number|String} Connect through an HTTP proxy when sending notifications

 - `manageChannelsProxy` {host: String, port: Number|String} Connect through an HTTP proxy when managing channels

 - `rejectUnauthorized` {Boolean} Reject Unauthorized property to be passed through to tls.connect() (Defaults to `true`)

 - `connectionRetryLimit` {Number} The maximum number of connection failures that will be tolerated before `apn.Provider` will "give up". [See below.](#connection-retry-limit) (Defaults to: 3)

 - `heartBeat` {Number} The delay interval in ms that apn will ping APNs servers. (Defaults to: 60000)

- `requestTimeout` {Number} The maximum time in ms that apn will wait for a response to a request. (Defaults to: 5000)

#### Provider Certificates vs. Authentication Tokens

Apple have introduced a new means of authentication with the APNs - [Provider Authentication Tokens][provider-auth-tokens]. These replace the old-style Certificate/Key pairs with tokens based on the [JWT][jwt] standard. The new system is superior in a number of ways:

 * A token key does not expire and therefore does not require annual renewal - no more outages when someone forgets to deploy the renewed certificate
 * Token keys are issued per-team - no need to manage one connection per app, just use the notification `topic` property to target a specific application on your connection
 * Tokens are valid for Production and Sandbox environments - certificates have also had this feature for a while but it's so nice it's worth mentioning again

In short: You should switch to using [Provider Authentication Tokens][provider-auth-tokens] _as soon as possible_.

##### Connection retry limit

TLS errors such as expired or invalid certificates will cause an error to be emitted, but in this case it is futile for `apn` to continue attempting to connect. There may also be other cases where connectivity issues mean that a process attempting to send notifications may simply become blocked with an ever-increasing queue of notifications.

To attempt to combat this a (configurable) retry limit of 10 has been introduced. If ten consecutive connection failures occur and no previous connections are still open then the `Provider` will trigger a failure for **all** pending notifications and no longer attempt to send them.

The `Provider` can continue to be used for sending notifications and the counter will reset.

## Class: apn.Provider

`apn.Provider` provides a number of methods for sending notifications, broadcasting notifications, and managing channels. Calling any of the methods will return a `Promise` for each notification, which is discussed more in [Results from APN Provider Methods](#results-from-apnprovider-methods).

### connection.send(notification, recipients)

This is the main interface for sending notifications. Create a `Notification` object and pass it in, along with a single recipient or an array of them, and node-apn will take care of the rest, delivering a copy of the notification to each recipient.

> A "recipient" is a `String` containing the hex-encoded device token.

Calling `send` will return a `Promise`. The Promise will resolve after each notification (per token) has reached a final state.

### connection.manageChannels(notification, bundleId, action)
This is the interface for managing broadcast channels. Create a single `Notification` object or an array of them and pass the notification(s) in, along with a bundleId, and an action (`create`, `read`, `readAll`, `delete`) and node-apn will take care of the rest, asking the APNs to perform the action using the criteria specified in each notification.

> A "bundleId" is a `String` containing the bundle identifier for the application.

> An "action" is a `String` containing: `create`, `read`, `readAll`, or `delete` and represents what action to perform with a channel (See more in [Apple Documentation](https://developer.apple.com/documentation/usernotifications/sending-channel-management-requests-to-apns)).

Calling `manageChannels` will return a `Promise`. The Promise will resolve after each notification has reached a final state.

### connection.broadcast(notification, bundleId)

This is the interface for broadcasting Live Activity notifications. Create a single `Notification` object or an array of them and pass the notification(s) in, along with a bundleId and node-apn will take care of the rest, asking the APNs to broadcast using the criteria specified in each notification.

> A "bundleId" is a `String` containing the bundle identifier for the application.

Calling `broadcast` will return a `Promise`. The Promise will resolve after each notification has reached a final state.

### Results from apn.Provider methods

 Each notification can end in one of three possible states:

  - `sent` - the notification was accepted by Apple for delivery to the given recipient
  - `failed` (rejected) - the notification was rejected by Apple. A rejection has an associated `status` and `reason` which are included.
  - `failed` (error) - a connection-level error occurred, which prevented successful communication with Apple. In very rare cases, it's possible that the notification was still delivered. However, this state usually results from a network problem.

When the returned `Promise` resolves, its value will be an Object containing two properties

#### sent

An array of device tokens or bundle identifiers to which the notification was successfully sent and accepted by Apple.

Being `sent` does **not** guarantee the notification will be _delivered_, other unpredictable factors - including whether the device is reachable - can ultimately prevent delivery.

#### failed

An array of objects for each failed token or bundle identifier. Each object will contain the device token or bundle identifier that failed and details of the failure, which will differ between rejected and errored notifications.

For **rejected** notifications using `send()`, the object will take the following form

```javascript
{
  device: "834c8b48e6254e47435d74720b1d4a13e3e57d0bf318333c284c1db8ce8ddc58",
  status: 410,
  response: {
    reason: "Unregistered"
  }
}
```

More details about the response and associated status codes can be found in the [HTTP/2 Response from APN documentation][http2-response].

If a failed notification using `send()` was instead caused by an **error** then it will have an `error` property instead of `response` and `status`:

```javascript
{
  device: "834c8b48e6254e47435d74720b1d4a13e3e57d0bf318333c284c1db8ce8ddc58",
  error: Error // An Error object containing details about the failure.
}
```

---
#### A note on Unicode.

If you wish to send notifications containing emoji or other multi-byte characters you will need to ensure they are encoded correctly within the JavaScript string. Notifications are transmitted to Apple in UTF-8 and provided the string is valid it will be encoded accordingly.

### connection.shutdown()

Indicate to node-apn that it should close all open connections when the queue of pending notifications is fully drained. This will allow your application to terminate.

**Note:** If notifications are pushed after the shutdown has started, an error will be thrown.

[provider-api]: https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html
[provider-auth-tokens]: https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html#//apple_ref/doc/uid/TP40008194-CH11-SW1
[http2-response]:
https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html#//apple_ref/doc/uid/TP40008194-CH11-SW2
[jwt]: https://jwt.io
