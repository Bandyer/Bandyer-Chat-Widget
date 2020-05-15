# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

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
