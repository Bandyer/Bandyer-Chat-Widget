# 1.25.0 (January 28, 2020)

- [Feature]: Handle new access-denied error in call
- [Feature]: New error for widget not initialized
- [Feature]: Add new UI for verification event
- [Feature]: User info in call view

- [Update]: (Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.8.0 version)
- [Update]: (Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.10.1 version)

# 1.24.2 (January 22, 2020)

- [Bug]: Fix createCall input validation

# 1.24.1 (January 21, 2020)

- [Feature]: Added timeout  in message fetch  for a better usability

- [Bug]: Fix channel creation, now the channels are private and use a REST API for the creation
- [Bug]: Updating dependencies to resolve vulnerabilities

# 1.24.0 (January 17, 2020)

- [Feature]: Add reconnect during the call
- [Feature]: New reconnecting loader during the call in case of disconnection
- [Feature]: Add local 'cache' system for messages
- [Feature]: Add pagination system for messages, fetch on scroll
- [Feature]: New info-bar for chat socket disconnected

- [Bug]: Fix change view on hang up call in window mode
- [Bug]: Fix UI during call in window mode on small screen
- [Bug]: Fix screen-share cut
- [Bug]: Fix snackbar visualization on IE
- [Bug]: Fix scrollToBottom on new message in case of change resolution
- [Bug]: Fix pending ringing audio after call answer and then call hang up

- [Update]: (Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.7.0 version)
- [Update]: (Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.10.0 version)

# 1.23.1 (January 02, 2020)

- [Bug]: handle error on many to many calls using joinCallURL API

- [Update]: (Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.6.1 version)

# 1.23.0 (Dicember 19,2019)

- [Feature]: add joinCallURL API

- [Update]: (Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.6.0 version)

# 1.22.1 (Dicember 18,2019)

- [Bug]: Fix background issue on conversation container
- [Bug]: Fix translations and spacing in dial in-out

# 1.22.0 (Dicember 17,2019)

- [Feature]: New composeMessage API
- [Feature]: Change default color and online badge UI

- [Bug]: Fix scroll icon
- [Bug]: Fix 'now' label for incoming messages

# 1.21.0 (Dicember 12,2019)

- [Feature]: Widget responsive
- [Feature]: Reduced bundle size

- [Bug]: Fix provider logic on selectChat

- [Update]: (Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.9.0 version)

# 1.20.1 (Dicember 06,2019)

- [Bug]: Fix translation for canVideo tooltip

# 1.20.0 (Dicember 05,2019)

- [Feature]: Add Gear(settings) : possibility to select input devices
- [Feature]: New permission logic
- [Feature]: Call with no audio/no video
- [Feature]: Fallback procedure for call: audio/video => audio upgradable => no audio/no video
- [Feature]: New box-sizing:border box rule for a better integration with other framework
- [Feature]: Red Audio and video ButtonIcon on permission denied
- [Feature]: Notify users of failures during call with informative snackbars

- [Bug]: Fix visualization for old channels type
- [Bug]: Fix close stream on pending getUserMedia after disconnected call
- [Bug]: Fix loader visualization when back to chat button is pressed
- [Bug]: Fix search in channels view, now the list is updated runtime
- [Bug]: Fix UI

- [Update]: (Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.8.0 version)

# 1.19.6 (November 13,2019)

- [Bug]: Fixed call termination bug on call socket disconnection, updated web-communication-center to remove reconnection

- [Update]: (Updated [@bandyer/web-communication-center](https://www.npmjs.com/package/@bandyer/web-communication-center) to 1.5.2 version)

# 1.19.5 (November 12,2019)

- [Bug]: Fix get members in addChannels

# 1.19.4 (November 11,2019)

- [Feature]: Add screenSharingExtensionURL parameter in create function
- [Bug]: Fix notification in conversation view
- [Bug]: Fix launcher icon
- [Bug]: Fix translation for install screenShare extension page

# 1.19.3 (November 7,2019)

- [Feature]: Add version getter
- [Bug]: Add babel runtime polyfill

# 1.19.2 (November 6,2019)

- [Bug]: Fix audio on back to chat from call
- [Bug]: Fix icon change on unpublish screenshare from chrome toolbar
- [Bug]: Fix notification on back to chat icon in call window
- [Bug]: Fix UI for reconnect loader

# 1.19.1 (November 4,2019)

- [Bug]: Fix babel setting

# 1.19.0 (November 4,2019)

- [Feature]: Add new graphics for call view
- [Feature]: New carousel logic, now bottom to top
- [Feature]: Add new unread message logic
- [Feature]: New error message on socket call error

- [Bug]: Fix polyfill system for IE
- [Bug]: Fix notification on back to call button
- [Bug]: Various UI adjustment

- [Update]: (Updated [@bandyer/web-core-av](https://www.npmjs.com/package/@bandyer/web-core-av) to 1.7.1 version)

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
