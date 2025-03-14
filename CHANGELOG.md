# [6.5.0](https://github.com/parse-community/node-apn/compare/6.4.3...6.5.0) (2025-03-13)


### Features

* Add `input-push-channel` and `input-push-token` to APS ([#177](https://github.com/parse-community/node-apn/issues/177)) ([a0f5230](https://github.com/parse-community/node-apn/commit/a0f5230983199747f38b621c84b196163a088474))

## [6.4.3](https://github.com/parse-community/node-apn/compare/6.4.2...6.4.3) (2025-02-11)


### Bug Fixes

* Does not allow sending the priority of 10 for notifications ([#173](https://github.com/parse-community/node-apn/issues/173)) ([689ce37](https://github.com/parse-community/node-apn/commit/689ce3734dcd5170ac7e16bb67f73551de6a6b74))

## [6.4.2](https://github.com/parse-community/node-apn/compare/6.4.1...6.4.2) (2025-02-08)


### Bug Fixes

* Security upgrade http-cache-semantics from 4.1.0 to 4.1.1 ([#125](https://github.com/parse-community/node-apn/issues/125)) ([d16213a](https://github.com/parse-community/node-apn/commit/d16213a33dbb0191021593cb34b2f3c84a7640c6))

## [6.4.1](https://github.com/parse-community/node-apn/compare/6.4.0...6.4.1) (2025-02-08)


### Bug Fixes

* Incorrectly attempting to send body in `GET`, `DELETE` requests ([#169](https://github.com/parse-community/node-apn/issues/169)) ([7ca2681](https://github.com/parse-community/node-apn/commit/7ca268162817dc3604eda46f9ff2433605075c9e))

# [6.4.0](https://github.com/parse-community/node-apn/compare/6.3.0...6.4.0) (2025-02-06)


### Features

* Add the ability to manage channels and send broadcasts ([#164](https://github.com/parse-community/node-apn/issues/164)) ([ab234c9](https://github.com/parse-community/node-apn/commit/ab234c92a53f71b5738e7ae6ca661ac6f75d556d))

# [6.3.0](https://github.com/parse-community/node-apn/compare/6.2.1...6.3.0) (2024-12-28)


### Features

* Add support for broadcast push notifications ([#163](https://github.com/parse-community/node-apn/issues/163)) ([ccd0781](https://github.com/parse-community/node-apn/commit/ccd0781d3c4f56ce8356eeca0fa050100967c6ae))

## [6.2.1](https://github.com/parse-community/node-apn/compare/6.2.0...6.2.1) (2024-11-14)


### Bug Fixes

* Security upgrade jsonwebtoken from 9.0.0 to 9.0.2 ([#159](https://github.com/parse-community/node-apn/issues/159)) ([868a427](https://github.com/parse-community/node-apn/commit/868a427bfcf8e3fadf54e9b98c359edef2f57be6))

# [6.2.0](https://github.com/parse-community/node-apn/compare/6.1.0...6.2.0) (2024-09-25)


### Features

* Add fields `subtitleLocKey`, `subtitleLocArgs` for localized subtitle and arguments in notifications ([#154](https://github.com/parse-community/node-apn/issues/154)) ([c885405](https://github.com/parse-community/node-apn/commit/c885405e10c9d1ec15968c42d410ce4f56dfbf04))

# [6.1.0](https://github.com/parse-community/node-apn/compare/6.0.2...6.1.0) (2024-09-16)


### Features

* Add `dismissal-date` property to Live Activity notifications ([#152](https://github.com/parse-community/node-apn/issues/152)) ([d863f2e](https://github.com/parse-community/node-apn/commit/d863f2e6ce2a58ee92371d69ad8966dd9927e90f))

## [6.0.2](https://github.com/parse-community/node-apn/compare/6.0.1...6.0.2) (2024-09-10)


### Bug Fixes

* Incorrect field name `events` instead of `event` in Live Activity push notification payload ([#148](https://github.com/parse-community/node-apn/issues/148)) ([5876a59](https://github.com/parse-community/node-apn/commit/5876a59fcd04c53ccd85ae8ea06a51e2cf119993))

## [6.0.1](https://github.com/parse-community/node-apn/compare/6.0.0...6.0.1) (2023-10-20)


### Bug Fixes

* Minimum required Node version in `engines.node` has not been upgraded to Node 14 ([#138](https://github.com/parse-community/node-apn/issues/138)) ([4eb3686](https://github.com/parse-community/node-apn/commit/4eb3686e30c225d8d83c55cf7a5f11bc807a9ef4))

# [6.0.0](https://github.com/parse-community/node-apn/compare/5.2.3...6.0.0) (2023-10-19)


### Features

* Add support for Node 18, 20 drop support for Node 12 ([#137](https://github.com/parse-community/node-apn/issues/137)) ([f203bc1](https://github.com/parse-community/node-apn/commit/f203bc1c6d1e72a5b0689368220ec109d347003a))


### BREAKING CHANGES

* This release removes support for Node 12; the minimum required version is Node 14. ([f203bc1](f203bc1))

## [5.2.3](https://github.com/parse-community/node-apn/compare/5.2.2...5.2.3) (2023-07-21)


### Bug Fixes

* Incorrect field name `event` instead of `events` in Live Activity push notification payload ([#133](https://github.com/parse-community/node-apn/issues/133)) ([a25c835](https://github.com/parse-community/node-apn/commit/a25c835d220a6d37101eeaedaec78e1fb0028696))

## [5.2.2](https://github.com/parse-community/node-apn/compare/5.2.1...5.2.2) (2023-07-20)


### Bug Fixes

* Shutdown callback is not passed from provider to client ([#118](https://github.com/parse-community/node-apn/issues/118)) ([9fa197f](https://github.com/parse-community/node-apn/commit/9fa197fd92da5a56f5bdaf7d8df8dab6e85af0d1))

## [5.2.1](https://github.com/parse-community/node-apn/compare/5.2.0...5.2.1) (2023-07-16)


### Bug Fixes

* Security upgrade jsonwebtoken from 8.5.1 to 9.0.0 ([#128](https://github.com/parse-community/node-apn/issues/128)) ([5bc179d](https://github.com/parse-community/node-apn/commit/5bc179dfe621fe3e225bcdffb98bc913c5745a0b))

# [5.2.0](https://github.com/parse-community/node-apn/compare/5.1.3...5.2.0) (2023-07-16)


### Features

* Add support for Live Activity with ActivityKit push notifications ([#130](https://github.com/parse-community/node-apn/issues/130)) ([80717cd](https://github.com/parse-community/node-apn/commit/80717cd6c3a3341c90d3a6ea73fe64c663de8c8a))

## [5.1.3](https://github.com/parse-community/node-apn/compare/5.1.2...5.1.3) (2022-03-27)


### Bug Fixes

* security upgrade node-forge from 1.2.1 to 1.3.0 ([#101](https://github.com/parse-community/node-apn/issues/101)) ([a713a2b](https://github.com/parse-community/node-apn/commit/a713a2b68663591de1c3eb69335dbd6cafcdf3e5))

## [5.1.2](https://github.com/parse-community/node-apn/compare/5.1.1...5.1.2) (2022-03-27)


### Bug Fixes

* security bump minimist from 1.2.5 to 1.2.6 ([#107](https://github.com/parse-community/node-apn/issues/107)) ([b2b1358](https://github.com/parse-community/node-apn/commit/b2b13585122d7c41d5b42e9428517aa9704b767f))

# [5.1.1](https://github.com/parse-community/node-apn/compare/5.1.0...5.1.1) (2022-03-27)

# Bug Fixes
- Various dependency upgrades to fix vulnerabilities

# 5.1.0

### Features
- Add support for iOS 15 property interruption-level ([#83](https://github.com/parse-community/node-apn/pull/83))
- Add support for target-content-id notification property ([#84](https://github.com/parse-community/node-apn/pull/84))

5.0.0
* Drop support for node versions prior to 12 - those node versions have bugs in the http2 library.
* Support MultiProvider and MultiClient to use a round-robin client for HTTP2.

4.1.1
* FIX: add proxy and fix logger types
* NEW: Added support for critical notifications

4.1.0
* NEW: Proxy support
* FIX: Close client on unexpected frame error
* NEW: Add a configurable info/error logger
* FIX: Update endpoint address
* FIX: Add support to zero valued expiry

4.0.0
* BREAKING: shutdown() function on client now destroy the client and future requests throw error
* Add test cases to Client
* Improve verbose messages
* Add request timeout handler
* Add a new config setting requestTimeout (defaults to 5000 milliseconds)
* Change ResponseFailure.status typing to be number
* Fix nits on typos in documentation
* Also run tests in Node 12 and 14
* Remove the unreferenced lib/protocol directory
* Improve GO AWAY handler

3.2.0
* Update node-forge and pin packages
* Add typings for the "voip" NotificationPushType
* Typed Notification.pushType

3.1.0
* Fix: http2session.shutdown() is not a function
* Update npm install command in README
* Add support for handling http2 GOAWAY messages and set http2 ping interval

3.0.6
* Set npm access to public in package.json to override default of private for scoped packages

3.0.5
* Change Travis to use node 10 instead of node 9
* Attempt changes to travis to get it to publish to npm

3.0.4
* No change, bumping version with travis enabled

3.0.3
* Create an npm installable package `@parse/node-apn`

3.0.2-parse:
* Fix 3.0.1-parse release

3.0.1-parse:
* Add support for apns-push-type key

3.0.0:
* Native Node.js HTTP/2 client
* Requires Node.js 8.9.1 or later
* Breaking changes:
    * The `status` property of notification results has changed from `string` to `number`

2.1.5:
* Improve typescript type definitions (#536)
* Several documentation improvements (#537, #547, #550, #555, #560, #560)
* Update dependencies (#566)
* Update .gitignore and add .nvmrc (#573)

2.1.4:
* Don't mutate passed in payload object
* Change APNs development endpoint to api.development.push.apple.com
* Update node-http2 fork

2.1.3:
* Add thread-id to notification payload (#484)
* Workaround an issue where APNS would return an HTTP 500 and make the connection unusable (#449, #480)
* Regularly renew JSON web token (#449, #480)

2.1.2:
* Add TypeScript type definitions (#441, #465)
* Update node-http2 fork to 3.3.6 and add stream.upstream not defined check (#444)

2.1.1:
* Fix broken logger (#438)
* Use archive URL for forked node-http2 module (#433)

2.1.0:

* JSON Web Token support (#401)
* Add `threadId` property for notifications
* Fix a leak caused when an error is emitted from the endpoint manager
    * Queued notifications would resolve as errored but would remain in the queue, leading them to be repeatedly rejected without termination and causing an error log from node

2.0.0:

* HTTP/2 Provider API (#277)
* `apn.Connection` has been renamed to `apn.Provider`
* `apn.Feedback` has been removed
* `apn.Device` has been removed - all tokens are now hex-encoded strings
* `apn.token` is provided to validate tokens and convert from `Buffer` if
  necessary
* Notifications are now required to have an associated `topic`
* `pushNotification(notification, tokens)` is now simply, `send(notification, recipients)`
* `send` returns a promise which will be fulfilled when all notifications have
  been sent (#362)
* Reliable Delivery (#168)
* Ability to mock `apn.Provider` behaviour
* Notification can be created in a "finished" state (#240)

1.7.8:

* Add support for Mutable Content (#413)

1.7.7:

* Fix Documentation URL (#393)
* Prevent `badge: 0` sending `badge: undefined` (#394)
* Avoid error, when deferredConnection is null (#397)

1.7.6:

* Emit an error when retry limit is exceeded (#333)
* Documentation fixes (#229, #343, #379)
* Reinstate broken aps behaviour (#377)

1.7.5:

* Notification property improvements
* Round-robin all open sockets when sending notifications
* `minConnections` option
* Prevent crashing when cancelling feedback multiple times (#307)
* Fix connection.shutdown behaviour (#299)
* Small doc improvements

1.7.4:

* Notification trim fixes. (#220)
* Notification refactoring
* `debug` package is now a dependency (#267)

1.7.3:

* Added support for increased payload length for VoIP applications (Closes #207)
* Fixed a bug with trimming UTF-16 encoded payloads
* Dropped support for node v0.6 as it doesn't support UTF-16 surrogate pairs. Plus it's old. It'll still work if needed though, if you use UTF-8.

1.7.2:

* Fixed: #238, only emit `error` when the problem is unrecoverable. Any use of `node-apn` should have an `error` listener attached to prevent uncaught exceptions.
* Various coding style improvements.
* CI.
* Removed legacy protocol support. I don't see any reason to keep it around, let me know if this causes you any problems.

1.7.1:

* Fixed: #224, always passing a CA value even if no certificates were specified. In this case the TLS library will not use the built in root certificates and will always fail to trust the server certificate.
* Changed: Socket timeout default has changed for disabled to 1 hour.
* Documentation fixes

1.7.0:

* Added: Credential validator to catch common configuration errors.
* Fixed: Documentation errors.

1.6.2:

* Updated maximum payload size to 2048 bytes. (See #181).
* Fixed: Feedback wouldn't include error message when emitting `feedbackError`.

1.6.1:

* Increased default cache length to 1000; Previous value of 100 was overly cautious.
* Added a delay of 100ms to connection to ensure notifications aren't lost if wrong certificates are used.
* Fixes #195: Better handling of socket creation
* Fixes #200: Improved buffer handling code when multiple connections are enabled.
* Minor optimisation to Notification processing, removing the need for 2 `JSON.stringify` calls
* Fixes #196: Check cache has contents before trying to access. Also ensure minimum size is "1" to allow "transmitted" events to be emitted.
* Fixes #199: Emit a "drain" event when no further notifications require sending. Most useful in a batch environment.

1.6.0:

* Fixes #156: Retire a socket from the pool immediately instead of waiting for a "close" event.
* Fixes #165: Introduced a connection retry limit to emit errors when fatal connection errors occur.
* Fixes #152: Failure to attach an error handler would prevent exponential backoff from working.
* Improved error handling for EPIPE write events to maximise chances of reading error info from Apple.
* Fixed #181: Initial support for larger payloads for iOS 8 testing.
* Fixed #187: Correctly trim notifications with escaped characters.
* Merged #190: Always emit a feedback event when batch mode is enabled, even if there are no tokens.
* Merged #189: Added support for iOS 8 Notification actions.
* Display a warning when null parameters are passed during connection creation.
* Fixed #171: Removed references to the unknown notification identifier.

1.5.2:

* Fixed #169, #170: Undesirable behaviour when PFX files are specified
* Fixes several problems identified after adding further test coverage.

1.5.0/1.5.1:

* **NOTE**: This version introduces a change to default behaviour: node-apn will now connect to the sandbox environment by default. Production mode must be explicitly specified. (Fixes #50, #146)

* Added option to disable Nagle Algorithm.
* Fixed #147: Error is not raised correctly when connection cannot be established.
* Fixed #151: Smarter certificate/key loading and simplified configuration parameters.
* Fixed #152: Exponential backoff when connect fails.
* Fixed #159: Alert Title and Alert Label are necessary for Safari Push Notifications.
* Fixed #161: Make `#setAlertText` chainable.
* Starting to create some tests. Lots more required!

This has been release as 1.5.1 due to a mistake with NPM.

1.4.4:

* Added a check when trying to resend notifications from cache (#138/#139)
* Don't set "aps" key if no well-known properties are present (#141)
* Fixed the notification `retryLimit` behaviour when set to 0. (#142)
* Added `batchSize` property for feedback.

1.4.3:

* Added `shutdown` method to hint to node-apn that all connections should be terminated after notifications have been sent. (#134)
* Fixed an exception thrown by an incorrect token length. (#133)

1.4.2:

* Added support for `url-args` property within the notification payload (Chad Scira, #129)
* Renamed `gateway` Connection parameter to `address` to avoid confusion with Feedback component.

1.4.0/1.4.1:

* New: Implements protocol launched with iOS 7 which permits specifying a notification priority.
* New: Ability to truncate notification body to nearest whole word.
* Fixed: TLS Connection stalled on node-0.11.x
* Fixed: Documentation defects.

1.3.8:

* Notifications now have a configurable number of retries. See `Notification.retryLimit` in docs.
* Fixed: Error wasn't raised on notifications if the module fails to initialise, they just perpetually lived on the queue.

1.3.7:

* Fixed: #14 Feedback event should be emitted once per connection, whether there are device tokens or not.

1.3.6:

* Resend notification if an error occurs before the socket drains (issue #100)
* Perform more error checking on device tokens. (issue #90)

1.3.5:

* Feedback now emits a `feedbackError` instead of `error` for socket errors.
* Fixed: Incorrect handling of errors when connection fails during TLS handshake.
* Added `Connection#setCacheLength()` for configuration of cache length during run-time.
* Notification confguration methods are now chainable.
* Updated documentation to point to new Apple Documentation URL.
* Added some more overview documentation.
* New example code.

1.3.4:

* Fixed #101: TypeError: Cannot call method 'resolve' of null

1.3.3:

* Fixed #98: Ensure `Notification#trim` cleanly trims Unicode characters.

1.3.2:

* Fixed #97: EventEmitter.listenerCount was only introduced in 0.9, no good for backward compatibility

1.3.1:

* Removed an unnecessary check that a `feedback` method had been specified on `Feedback` constructor.
* Added a debug warning when a listener hasn't been added on `Feedback`.

1.3.0:

This release represents a major re-think with how the module should function, it brings much needed functionality, dramatically improved reliability and lays foundations for future plans to increase message throughput.

* New API (`Connection#pushNotification`) to support sending one notification to multiple devices. (Please see `doc/Migration.markdown` for more info)
* Updated feedback service to emit events.
* Switched to `q` v0.9.x
* Added `buffersNotifications` option to allow disabling automatic resending.
* Fixed `Notification#Trim()` for multibyte strings
* New `fastMode` to aggressively deliver notifications (Only recommended for "worker" applications where node-apn is servicing a queue as it may impact responsiveness under heavy workload)
* Support for opening multiple connections to the push service. This option doesn't seem to offer any benefits yet, please let me know if you find otherwise.
* Improvements to better support node 0.10.x
* Better device token sanitisation in `Device`
* Minimise EPIPE errors
* Other small bug fixes

1.2.6:

* Added mdm support.
* Constrained 'q' module to 0.8.x because 0.9.0 is API incompatible.
* Fixed a `trim()` bug when compiling notification.
* ***NOTICE:*** v1.3.0 which will be released soon will break some API compatibility with error handling and there will be a new sending API (the legacy sending API will remain)

1.2.5:

* Introduced a new event model. The connection class is now an event emitter which will emit events on connection state changes. This should largely replace the existing, somewhat inadequate error handling in previous versions. Please see the section above for more details or the message on commit d0a1d17961
* Fixed a bug relating to rejecting unauthorized hosts
* Added support for PFX files instead of separate Certificate and Key Files
* Added a batched feedback feature which can callback with an array of all devices instead of calling the method for each device separately
* Added support for error callbacks on a per notification basis.
* Changed the socket behaviour to enable the TCP Nagle algorithm as recommended by Apple
* Fixed lots of small bugs around connection handling which should make high volume applications more stable. Node should no longer crash completely on EPIPE errors.
* Added connection socket timeout after a period of inactivity, configured by ```options.connectionTimeout```. The socket will then be re-established automatically if further notifications are sent.
* Added cache autoadjustment. If ```options.autoAdjustCache = true``` and a notification error occurs after the notification is purged from the cache the library will attempt to increase the cache size to prevent it happening in future.

1.2.4:

* Fixed some typos in the feedback methods
* Added some debug messages available during development, see debug section above.

1.2.3:

* Added some more error handling to the connection methods.
* Fixed a problem where an error handler was not bound to the correct context and wouldn't fire.

1.2.2:

* Fixes issue #47, Syntax Error in feedback.js

1.2.1:

* Earlier versions had some incorrect logic in the handling of reconnection. This should be fixed now
* Issue #46 ```.clone()``` did not set the badge property correctly.

1.2.0:

* Complete rewrite of the connection handling.
* [q][q] is now required.
* Change in the error handling logic. When a notification errors and it cannot be found in the cache, then all notifications in the cache will be resent instead of being discarded.
* `errorCallback` will also be invoked for connection errors.
* New methods on `Notification` to aid settings the alert properties.
* `content-available` can now be set for Newsstand applications by setting the `newsstandAvailable` property on the Notification object.
* `Notification` objects now have a `.clone(device)` method to assist you in sending the same notification to multiple devices.
* Included some js-doc tags in the source.
* Device object now provides a `.toString()` method to return the hex representation of the device token.
* Fixes #23, #28, #32, #34, #35, #40, #42

1.1.7:

* Fixes a problem with sockets being closed on transmission error causing EPIPE errors in node.
* Issues #29, #30

1.1.6:

* Fixes a regression from v1.1.5 causing connections to stall and messages to not be sent.

1.1.5:

* Feature: Certificate and Key data can be passed directly when creating a new connection instead of providing a file name on disk. (See: `certData` and `keyData` options)
* Deliver whole write buffer if the socket is ready.
* Fixed some global memory leaks.
* Tidied up some code formatting glitches flagged by jslint
* Fixes #16, #17, #18, #19, #20

1.1.4:

* Fixes #15: Sending unified emoji via apn; Added encoding parameter when sending notification

1.1.3:

* Fixes #11,#12,#13,#14: Ensure delivery of notifications to Apple even under heavy load.

1.1.2:

* Fixes #9, Addresses an issue if the socket disconnects with queued notifications it would be reinitialised before its teardown is completed leaving the system in an undefined state.

1.1.1:

* Fixes issue #6 where a socket emitting an error could bring down the whole node instance as the exception is uncaught.

1.1.0:

* First shot at node-0.4.0 compatibility with new tls API.
* Fixed a bug with parsing device token which could cause an out-of-bounds error.

1.0.4:

* The 1.0.x tree is now a maintenance branch as the TLS API used has been deprecated as of node 0.4.0
* Changed package.json to specify the inoperability of this version with node > 0.4.0

1.0.3:

* Fixes a typo in the documentation in this very file

1.0.2:

* Fixes critical issue with error callback not firing (Issue #1)

1.0.1:

* Moved some object methods into the prototype to save memory
* Tidied up some connecting code
* Introduced an `index.js` to make module loading tidier
* Fixed a couple of typos.

1.0.0:

* Well I created a module; Version 0.0.0 had no code, and now it does, and it works, so that's pretty neat, right?
