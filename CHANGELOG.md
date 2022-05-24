# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## Unreleased

## [2.1.3] - 2022-05-24
### Fixed
- Fix dependencies for npm and yarn install

## [2.1.2] - 2022-05-23
### Fixed
- fix window mode

## [2.1.1] - 2022-05-20
### Fixed
- npm build version

## [2.1.0] - 2022-05-20
### Added
- Support for us region
### Fixed
- npm package

## [2.0.0] - 2022-05-13
### Added
- Snackbar for recording state
### Changed
- Remove recording parameter in config
- Add 'none' to recordingType parameter
- Update [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to v3.2.2
- Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.19.0 version
### Fixed
- Window mode dismiss
- Improve widget lifecycle
- Avoid click during manual recording pending request

## [2.0.0-beta.1] - 2022-04-26
### Fixed
- Widget initialization with no tools
- Fix destroyClient

## [2.0.0-beta.0] - 2022-04-26
### Added
- New library exposure
- New configuration method
- Client object with new lifecycle, methods and events
- CallView and Call object with new methods and events
- ChannelView and Channel object with new methods and events
- Message object
- Information for recording call in dialing UI
- New authentication based on appId, region, environment, userId and accessToken
- New indian region support

### Changed
- Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to v3.1.0
- Update bandyer-chat-sdk to v2.1.0
- Rename record to recording in configuration
- Change default language to 'en'
- Change default tools behavior 
- Library name from BandyerChat to BandyerSDK
- Change all userAlias reference to userId
- Error system

### Removed
- Remove all the previous api from the BandyerChat
- Remove deprecated parameters
- Remove all the previous events
- Remove support for old authentications

### Fixed
- Window mode close
- Fix css problems with headers

## [1.45.1] - 2022-03-15
### Fixed
- Avoid incorrect behavior for getUserStatus

## [1.45.0] - 2022-01-17
### Added
- Authentication with accessToken
- Add inactive view for a session expired
### Changed
- Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.17.0
### Fixed
- Logout for chat
- Notification after a re-login

## [1.44.2] - 2021-12-20
### Fixed
- Chat update token after disconnection

## [1.44.1] - 2021-12-17
### Fixed
- JoinCallUrl in embed mode
- Avoid joinCallUrl for MTM

## [1.44.0] - 2021-12-03
### Added
- New feedback view
- New feedback param in config, default to false
- New chat sdk
- New status info in chat
### Changed
- Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.16.0
### Fixed
- Fix Ui bugs for chat
- Participants limit in createCall

## [1.43.0] - 2021-10-27
### Added
- Add view that handle for force disconnect event
### Changed
- Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.15.0

## [1.42.0] - 2021-10-12
### Added
- Add isAdmin and recordingType param in config
### Changed
- Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.14.0
- Update createCall API, allow record, recording, recordingType and isAdmin param in option field

## [1.41.7] - 2021-09-27
### Fixed
- Fix joinCallUrl in window mode

## [1.41.6] - 2021-09-24
### Fixed
- Fix loop on ask autoplay permission prompt
- Fix italian translations

## [1.41.5] - 2021-07-14
### Changed
- Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.17.1 version

## [1.41.4] - 2021-06-03
### Changed
- Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.13.5
### Fixed
- Fix error after a multiple call in window mode

## [1.41.3] - 2021-05-28
### Fixed
- Fix channels visualization when the twilio channels limit is reached

## [1.41.2] - 2021-05-25
### Changed
- Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.13.3

### Fixed
- Fix incoming call when the user was busy in an MTM call
- Fix widget re-instance after a logout failure

## [1.41.1] - 2021-05-12
### Fixed
- Fix stream recovery on a stream fail
- FIx stream close on room disconnect
- Fix unexpected crash when the window mode is closed for network issues

## [1.41.0] - 2021-04-26
### Added
- Add virtual background capability on safari on macOS
- Add virtual background capability on supported android browsers

### Changed
- Improve virtual background
- Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.17.0 version

## [1.40.0] - 2021-04-13
### Added
- Add event and executor information to dial and call events

### Changed
- Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.13.0


## [1.39.7] - 2021-04-09
### Fixed
- Fix notifications on select chat when the chat is closed

## [1.39.6] - 2021-04-06
### Fixed
- Fix notifications badge when a chat is selected and the widget was closed

## [1.39.5] - 2021-03-19
### Changed
- Change callee forwarding, align with others sdk

## [1.39.4] - 2021-03-12
### Fixed
- Fix call style from layout config

## [1.39.3] - 2021-03-08
### Fixed
- Fix languages
- Fix channels view message when the last channel was removed

## [1.39.2] - 2021-01-18
### Fixed
- Fix sdkCommon error while npm import

## [1.39.1] - 2021-01-18
### Changed
- Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.16.1 version

## [1.39.0] - 2021-01-15
### Added
- Add menu that allows to choose the screenshare type (fps management)

### Changed
- Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.16.0 version

### Fixed
- FIx crash on search channels during loading

## [1.38.2] - 2021-01-08
### Fixed
- Fix consistency of hide status, now the widget maintain the status after each call

## [1.38.1] - 2020-12-23
### Changed
- Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.12.1

### Fixed
- Fix shutdown return value
- Fix disconnect call on shutdown

## [1.38.0] - 2020-12-17
### Added
- Add tools param in create api
- Add forwarding of tools in window mode
- Add forwarding of virtualBackground param in window mode

### Changed
- Deprecate chat param, now is included in tools

### Fixed
- Fix an error that causes the unexpected closure of the call window while forwarding the provided user details

## [1.37.1] - 2020-12-16
### Changed
- Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.15.1 version

### Fixed
- Fix issue on virtual background and blur

## [1.37.0] - 2020-12-11
### Changed
- Split audio/video tag
- Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.15.0 version

### Fixed
- Fix video in gear on apple mobile devices

## [1.36.1] - 2020-11-19
### Fixed 
- Fix chat authentication
- Fix addChat issue with channel duplication

## [1.36.0] - 2020-10-23
### Added
- Added virtualBackground param in config that allow to automatically publish with a virtual background

### Changed
- Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.14.0 version

## [1.35.1] - 2020-10-22
### Changed
- Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.13.1 version

### Fixed
- Remove virtualbackground feature in Safari due to a bug 
- Fixed replace background freeze

## [1.35.0] - 2020-10-20
### Added
- Add virtual background capability that allows blurring or replace the background

### Changed
- Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.12.0
- Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.13.0 version

## [1.34.2] - 2020-09-30
### Changed
- Improve chat initialization

## [1.34.1] - 2020-09-22
### Changed
- Update call on dial answered to support new participants that make a join
- Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.11.1

## [1.34.0] - 2020-09-18
### Added
- Add manual recording functionality in gear when the room has manual recording enabled and the user is admin

### Changed
- Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.12.0 version
- Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.11.0

## [1.33.5] - 2020-09-11
### Fixed
 - Fix recording for incoming recording call
 
## [1.33.4] - 2020-09-10
 ### Changed
 - Change return value from joinCallURL, now return a call object

## [1.33.3] - 2020-08-31
 ### Fixed
 - Fix promise resolve on addChat method
 
## [1.33.2] - 2020-07-31
 ### Fixed
 - Fix error on addChat and removeChat due to a eslint issue while importing bandyerService
 
## [1.33.1] - 2020-07-31
 ### Changed
 - Change CSS obfuscation, now is Bandyer-[className]

## [1.33.0] - 2020-07-31
 ### Changed
 - Provide userDetails to callPage when the widget is in window mode
 
 ### Fixed
 - Fix promise return value problem using the addChat api

## [1.32.2] - 2020-07-15
### Added
- Add pointer-events: none to the container
- Add pointer-events: all to all the sub components

### Fixed
- Fix css dimensions

## [1.32.1] - 2020-07-08
### Fixed
- Fix subscribe streams in data only

## [1.32.0] - 2020-07-02
### Added
- Add chat param in widget initialize, allow to disable chat funtionality

## [1.31.4] - 2020-06-25

### Fixed
- Fix issue on userDetailsProvider during  ongoingCall when the chat isn't added
- Fix issue on createCall using userDetailsFormatter without the chat initilized

## [1.31.3] - 2020-06-11

### Fixed
- Fix muteAudio while moving a video from a container to another

## [1.31.2] - 2020-05-22

### Fixed
- Handling answered on another device

## [1.31.1] - 2020-05-21

### Fixed
- Fix slow userdetails initialization that  in some cases causes a 'get of undefined' error

## [1.31.0] - 2020-05-15

### Added

- Add return obj on createCall, add the possibility to hangUp the call

### Changed

- Changed getUser, now return an object{userAlias, status}

### Fixed

- Fix getUsersStatusList
- Fix errors on createCall

## [1.30.0] - 2020-05-13

### Added

- Add obfuscation to all CSS className
- Add prefix on materialUI classes for a better integration
- Add chat loadings information
- Add error on action already taken from another device on dial view
- Disable screesharing feature on ipadOS

### Changed

- Change polyfill, remove global polyfill for a better integration
- Hide the widget after a call when the previous state was hidden
- Change user_connected and user_disconnected events
- Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.11.1 version

### Fixed

- Fix full-screen style
- Fix call UI in mobile view
- Fix video muted in gear
- Fix IE plugin install prompt and lifecycle


## [1.29.0] - 2020-04-07

### Added

- Added call_started and call_ended events
- Added callDirection on all call events

### Changed

- Changed emit for call events, now all the events are generated for both users
- Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.10.0 version

### Fixed

- Fix call events when it is in window mode


## [1.28.0] - 2020-03-17

### Changed

- Changed call events ( incoming_call, call_dial_answered, call_dial_declined, call_dial_stopped ) return value [ see notes for further information ]


### Fixed

- Fix call events

### Notes

The return values ​​of the following call-related events have been filtered
- incoming_call
- call_dial_answered
- call_dial_declined
- call_dial_stopped

The structure of returned objects will have the following information:

| Key | Type | Description |
| --------- | :----------: | ----------- |
| callAlias | String | Unique alias of the current call |
| callParticipants | Array | Array of userAlias of the participants |
| callOptions | Object | Basic information about the call |


## [1.27.1] - 2020-03-16

### Fixed

- Fix addChat API
- Fix removeChat API


## [1.27.0] - 2020-02-21

### Added

- New file share feature in call
- Notification badge on new downloadable file

### Changed

- Info message when there are no chats
- New default UI for messages in conversation
- Removed delete option from conversation header
- Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.9.0 version

### Fixed

- Fixed avatar issue in mobile devices
- Fix language for online filter
- Fix remove chat
- Fix error message on add and remove chat from API
- Fix UI

## [1.26.3] - 2020-02-18

### Fixed

- Fixed issue on userDetailsProvider
- Fix avatar using provider in call
- Fix options in createCall

## [1.26.2] - 2020-02-11

### Fixed

- Fixed issue on verified false event

## [1.26.1] - 2020-02-07

### Fixed

- Fixed issue on verified icon

## [1.26.0] - 2020-02-06

### Added

- Send update attributes on mute audio/video
- New filter by status

### Changed

- New UI on mute video
- Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.10.2 version

### Fixed

- Fixed channel status on user already online
- Fixed animation on call button

## [1.25.0] - 2020-01-28

### Added

- Handle new access-denied error in call
- New error for widget not initialized
- Add new UI for verification event
- User info in call view

### Changed

- Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.8.0 version
- Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.10.1 version

## [1.24.2] - 2020-01-22

### Fixed

- Fix createCall input validation

## [1.24.1] - 2020-01-21

### Changed

- Added timeout  in message fetch  for a better usability

### Fixed

- Fix channel creation, now the channels are private and use a REST API for the creation
- Updating dependencies to resolve vulnerabilities

## [1.24.0] - 2020-01-17

### Added

- Add reconnect during the call
- New reconnecting loader during the call in case of disconnection
- Add local 'cache' system for messages
- Add pagination system for messages, fetch on scroll

### Changed

- New info-bar for chat socket disconnected
- Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.7.0 version
- Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.10.0 version

### Fixed

- Fix change view on hang up call in window mode
- Fix UI during call in window mode on small screen
- Fix screen-share cut
- Fix snackbar visualization on IE
- Fix scrollToBottom on new message in case of change resolution
- Fix pending ringing audio after call answer and then call hang up

## [1.23.1] - 2020-01-02

### Fixed

- handle error on many to many calls using joinCallURL API

### Changed

- Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.6.1 version

## [1.23.0] - 2019-12-19

### Added

- add joinCallURL API

### Changed

- Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.6.0 version

## [1.22.1] - 2019-12-18

### Fixed

- Fix background issue on conversation container
- Fix translations and spacing in dial in-out

## [1.22.0] - 2019-12-17

### Added

- New composeMessage API
- Change default color and online badge UI

### Fixed

- Fix scroll icon
- Fix 'now' label for incoming messages

## [1.21.0] - 2019-12-12

### Added

- Widget responsive

### Chnaged

- Reduced bundle size
- Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.9.0 version

### Fixed

- Fix provider logic on selectChat

## [1.20.1] - 2019-12-06

### Fixed

- Fix translation for canVideo tooltip

## [1.20.0] - 2019-12-05

### Added
- Add Gear(settings) : possibility to select input devices
- Permission logic
- Call with no audio/no video
- Fallback procedure for call: audio/video => audio upgradable => no audio/no video
- Red Audio and video ButtonIcon on permission denied
- Notify users of failures during call with informative snackbars

### Changed

- New box-sizing:border box rule for a better integration with other framework
- Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.8.0 version

### Fixed
- Fix visualization for old channels type
- Fix close stream on pending getUserMedia after disconnected call
- Fix loader visualization when back to chat button is pressed
- Fix search in channels view, now the list is updated runtime
- Fix UI

## [1.19.6] - 2019-11-13

### Changed

(Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.5.2 version

### Fixed

- Fixed call termination bug on call socket disconnection, updated web-communication-center to remove reconnection

## [1.19.5] - 2019-11-12

### Fixed

- Fix get members in addChannels

## [1.19.4] - 2019-11-11

### Added

- Add screenSharingExtensionURL parameter in create function

### Fixed

- Fix notification in conversation view
- Fix launcher icon
- Fix translation for install screenShare extension page

## [1.19.3] - 2019-11-07

### Added

- Add version getter

### Changed

- Add babel runtime polyfill

## [1.19.2] - 2019-11-06

### Fixed

- Fix audio on back to chat from call
- Fix icon change on unpublish screenshare from chrome toolbar
- Fix notification on back to chat icon in call window
- Fix UI for reconnect loader


## [1.19.1] - 2019-11-04

### Fixed

- Fix babel setting

# [1.19.0] - 2019-11-04

### Added

- Add new graphics for call view
- Add new unread message logic
- New error message on socket call error

### Changed

- New carousel logic, now bottom to top
- Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.7.1 version

### Fixed

- Fix polyfill system for IE
- Fix notification on back to call button
- Various UI adjustment

# 1.18.0 (October 22,2019)

- [Feature]: Add usersDetailsProvider
- [Feature]: Add usersDetailsFormatter
- [Feature]: Add back to call button in channels view
- [Feature]: Add notification on back to chat button

- [Bug]: Bug fix for screenShare
- [Bug]: Bug fix for toolTip
- [Bug]: Bug fix traduction for search component

- [Update]: (Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.7.0 version)

# 1.17.1 (October 15,2019)

- [Feature]: Add search channel component

# 1.17.0 (October 14, 2019)

- [Feature]: Add createCall programmatically
- [Feature]: Add possibility to back to chats when there is an active call
- [Feature]: Add reconnect view that inform the user if there is a network issue

- [Bug]: Bug fix for translation
- [Bug]: Bug fix for renew twilio token
- [Bug]: Bug fix for online status
- [Bug]: Bug fix for keep update multi-instance message sent by the same user
- [Bug]: Bug fix for recording feature
- [Bug]: Bug fix for stop screen-sharing using browser Stop button

- [Update]: (Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.6.0 version)
- [Update]: (Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.5.1 version)

# 1.16.2 (April 16, 2019)

-   [Bug]: bug fix for channels with old attributes structure

# 1.16.1 (April 10, 2019)

-   [Bug]: minor bug fix

# 1.16.0 (April 10, 2019)

-   [Feature]: widget handles the user presence with a badge indicator.

# 1.15.0 (March 29, 2019)

-   [Update](Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.5.1 version) - Firefox min version 52 )

# 1.14.2 (March 15, 2019)

-   [Update](Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.5.0 version) - GUM with no mic )
-   Bug fix

# 1.14.1 (March 6, 2019)

-   Fix upgrade video event from window
-   "chat_loaded" event added

# 1.14.0 (March 5, 2019)

-   [Update](Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.4.8 version) - Fix participant status logic in call )
-   [Update](Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.4.4 version) - Screen sharing in Chrome 72 without extension )

# 1.13.7 (February 28, 2019)

-   Fix call type audio_upgreadable when callType is audio_video#2

# 1.13.6 (February 27, 2019)

-   Fix call type audio_upgreadable when callType is audio_video

# 1.13.5 (February 26, 2019)

-   [Update](Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.4.4 version) - Fix handleRoomParticipantStatusChanged bug
-   Fix double click actions in createRoom and answer

# 1.13.4 (February 21, 2019)

-   [Update](Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.4.3 version) - Fix handleRoomParticipantStatusChanged bug

# 1.13.3 (February 20, 2019)

-   Fixed header font size CSS rule

# 1.13.2 (February 20, 2019)

-   Fixed user_disconnected event

# 1.13.1 (February 19, 2019)

-   Fixed problem in answer method

# 1.13.0 (February 19, 2019)

-   Call mode 'window' or 'embed'
-   Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.4.1 version

# 1.12.0 (January 31, 2019)

-   Add getUsersList method
-   Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.3.0 version

# 1.11.0 (January 25, 2019)

-   Forward call events in Client Object
-   Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.2.5 version

# 1.10.0 (January 9, 2019)

-   Add platform info in channel and message
-   Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.1.0 version

# 1.9.2 (December 20, 2018)

-   Bug fix in delete channel button (either in channels or conversation view)

# 1.9.1 (December 19, 2018)

-   Bug fix in mobile call (stream attributes)

# 1.9.0 (November 29, 2018)

-   Enabled Edge videocall and Screen sharing
-   Bug fix for answer and decline methods (action already taken error)
-   Bug fix subscribe stream in room connected

# 1.8.0 (November 23, 2018)

-   Widget use new SDK [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) and [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center)
-   Delete channel directly in the frontend
-   Call type option in the create method with audio_only, audio_upgradable and audio_video
-   Bug fixes

# 1.7.0 (October 25, 2018)

-   Widget supports record option in .create method
-   Responsive design for mobile support

# 1.6.0 (September 28, 2018)

-   Publish / unpublish logic for SS (not replaceTrack)
-   IE SS enabled

# 1.5.1 (September 19, 2018)

-   Notification badge fixed
-   Notification badge for every channel in channel list view
-   Bug fixes

# 1.5.0 (July 20, 2018)

-   Configurable layout with different options (header, body, launcher, etc)
-   Bug fixes

# 1.4.0 (July 20, 2018)

-   Handle isTyping, messageSent and messageReceived events
-   New methods: getLastMessageSent, getLastMessageReceived, toggleWidget, closeWidget and openWidget

# 1.3.0 (July 13, 2018)

-   Handle IE Plugin & Install (No ScreenSharing)

# 1.2.0 (July 06, 2018)

-   Handle screen sharing installation

# 1.1.1 (June 23, 2018)

-   Fixed bug in screen sharing button
-   Fixed bug in handleNewChat with hidden mode true
-   Call with reduce to icon enabled

# 1.1.0 (June 22, 2018)

-   Screen sharing enabled in Chrome (with extension) and Firefox (no extension)
-   New methods: showChat, hideChat. Useful to show or hide the widget in the HTML page
-   New options: hidden, start the widget in hidden mode.

# 1.0.2 (June 07, 2018)

-   Fixed add chat for older versions support (0.x.x)

# 1.0.1 (June 01, 2018)

-   Fixed Log Level

# 1.0.0 (June 01, 2018)

#### **Breaking change**

-   Video call fully integrated inside widget
-   Interact with Bandyer mobile sdk
-   Improved performance and security

# 0.1.6 (March 02, 2018)

-   Fixed global SCSS style (responsive query)

# 0.1.5 (March 02, 2018)

-   Minor css fixes

# 0.1.4 (March 02, 2018)

-   Fixed global SCSS style

# 0.1.3 (January 24, 2018)

-   Fixed method create, now it return a Promise

# 0.1.2 (November 30, 2017)

-   Fix README

# 0.1.1 (November 29, 2017)

-   Initial public release
