# BANDYER CHAT WIDGET

Bandyer widget chat is a fast and effective way to offer live chat and videochat in your application.


### Consuming a library
You can consume the library from NPM:

`npm install @bandyer/bandyer-chat-widget`

For browser you can also use the version from CDN:


`<script src="https://cdn.bandyer.com/sdk/js/chat/X.X.X/bandyer-widget.min.js"
type="text/javascript" ></script>`


> Example embed in HTML page;

```html
<html>
<head></head>
	<body>
	<script src="https://cdn.bandyer.com/sdk/js/chat/X.X.X/bandyer-widget.min.js" type="text/javascript" >
	</script>
	</body>
</html>
```

The widget attaches in the window object of the HTML page the **BandyerChat** global variable.

#### Browser support

This widget is supported by Google Chrome and Firefox without any plugin.
For IE11 support you need to install a plugin and include the following polyfill: 
`https://babeljs.io/docs/en/babel-polyfill`



#### Screenshots

<img src="https://cdn.bandyer.com/sdk/js/resources/screenshots/bandyer-chat-widget-widget-channels-open-600.jpg" alt="Drawing" style="height: 300px;"/>
<img src="https://cdn.bandyer.com/sdk/js/resources/screenshots/bandyer-chat-widget-widget-chat-open-600.jpg" alt="Drawing" style="height: 300px;"/>
<img src="https://cdn.bandyer.com/sdk/js/resources/screenshots/bandyer-chat-widget-ringingin-600.jpg" alt="Drawing" style="height: 300px;"/>



### Create 
> .create()

```javascript
const Client = BandyerChat.create({
	userAlias: 'usr_123456', 
	appId: 'wAppId_fake123456', 
	environment: 'sandbox',
	hidden: false,
	screenSharingExtensionId: 'id of your screen sharing extension'
});

```

`.create({userAlias: 'usr_123456', appId: 'wAppId_fake123456', environment: 'sandbox', hidden: false})`

Configuration of a new widget instance is made by calling .create() method. The options required are the following:

### Create Parameters

| Parameter | Required | Default | Description |
| --------- | :----------: | :------:| ----------- |
| userAlias | yes |"" | The widget who initialize the widget |
| appId | yes | "" | A valid appId. Please contact Bandyer to have a valid appId |
| environment | yes | "" | Sandbox or production are the permitted values. |
| hidden | no | false | Create the widget in hidden mode (not visibile in the HTML). |
| screenSharingExtensionId | no | '' | Extension ID of the Screen Sharing Extension. |

##### Returns:
###### Type

Promise.<(Client|Error)>

### Client 

A Client is a starting point to access Bandyer Chat functionality. It is possible to listen events which are fired by the widget. A Client is returned by the create method.

```javascript
const Client = BandyerChat.create({
	userAlias: 'usr_123456', 
	appId: 'wAppId_fake123456', 
	environment: 'sandbox',
	hidden: false,
	screenSharingExtensionId: 'id of your screen sharing extension'
});

```

#### Events

#### typingStarted

```javascript
Client.on('typing_started',(data) => {
	// your logic
});
```

Fired when a User has started typing.
> Note: To optimise network traffic, Client endpoints will only send a Typing signal once every 5 seconds

###### Type
| Key | Type | Description |
| --------- | :----------: | ----------- |
| userAlias | String | Alias of the user |
| chat | String | Unique identifier of the chat |
| participants | Array | Array of participants |

#### messageSent

```javascript
Client.on('message_sent',(data) => {
	// your logic
});
```

Fired when a User has sent a message.

###### Type
| Key | Type | Description |
| --------- | :----------: | ----------- |
| id | String | Unique identifier of the message |
| chat | String | Unique identifier of the chat |
| participants | Array | Array of participants |
| text | String | Text of the message |
| timestamp | Date | When message was created |
| sender | String | User alias of the creator of the message |

#### messageReceived

```javascript
Client.on('message_received',(data) => {
	// your logic
});
```

Fired when a User has received a message.

###### Type
| Key | Type | Description |
| --------- | :----------: | ----------- |
| id | String | Unique identifier of the message |
| chat | String | Unique identifier of the chat |
| participants | Array | Array of participants |
| text | String | Text of the message |
| timestamp | Date | When message was created |
| sender | String | User alias of the creator of the message |

#### messageRead

```javascript
Client.on('message_read',(data) => {
	// your logic
});
```

Fired when a User has read a message.

###### Type
| Key | Type | Description |
| --------- | :----------: | ----------- |
| id | String | Unique identifier of the message |
| chat | String | Unique identifier of the chat |
| participants | Array | Array of participants |
| text | String | Text of the message |
| timestamp | Date | When message was created |
| sender | String | User alias of the creator of the message |

#### User connection

```javascript
Client.on('user_connected',(data) => {
	// your logic
});
```

Fired when a User connects to the platform.

###### Type
| Key | Type | Description |
| --------- | :----------: | ----------- |
| user.userAlias | String | User alias of the user |
| user.firstName | String | Firstname of the user |
| user.lastName | String |Lastname of the user |
| user.email | String | Email of the user |
| user.image | String | Image of the user |
| user.role | Number | Role of the user |
| status | String | Current status (ONLINE, OFFLINE, BUSY) |

#### User disconnection

```javascript
Client.on('user_disconnected',(data) => {
	// your logic
});
```

Fired when a User disconnects to the platform.

###### Type

| Key | Type | Description |
| --------- | :----------: | ----------- |
| user.userAlias | String | User alias of the user |
| user.firstName | String | Firstname of the user |
| user.lastName | String |Lastname of the user |
| user.email | String | Email of the user |
| user.image | String | Image of the user |
| user.role | Number | Role of the user |
| status | String | Current status (ONLINE, OFFLINE, BUSY) |


### Add chat
> .addChat()

```javascript
BandyerChat.addChat('usr_fr55ga3');
```

`.addChat('usr_fr55ga3')`

To enable the chat with another user of your platform, you need to call the .addChat() method. 
The addChat method expect a valid user alias (it must be a user already created). Once the method is called, the widget will display the chat added.

**Note:** if the widget is in hidden mode, the addChat method mode will display the widget.

##### Returns:
###### Type

Promise.<(void|Error)>

### Remove chat

> .removeChat()

```javascript
BandyerChat.removeChat('usr_fr55ga3');
```

`.removeChat('usr_fr55ga3')`

To remove a chat you need to call the .removeChat() method. The removeChat will remove the chat between the user authenticated and the user specified as input of the method. All the messages between them will be deleted permanently.

##### Returns:
###### Type

Promise.<(void|Error)>

##### Returns:
###### Type

Promise.<(void|Error)>

### isAuthenticated
> .isAuthenticated()

```javascript
BandyerChat.isAuthenticated();
```

`.isAuthenticated()`


To check if the current istance of the widget is authenticated, you need to call the .isAuthenticated() method. The method will return **true** if the widget is authenticated, false otherwise.

##### Returns:
###### Type

Type: boolean

### Show widget
> .showChat()

```javascript
BandyerChat.showWidget();
```

`.showChat()`


Show the widget in the html page.

##### Returns:
###### Type

Type: Boolean.(true|false)>

### Hide widget
> .showChat()

```javascript
BandyerChat.hideWidget();
```

`.hideChat()`


hide the widget in the html page.

##### Returns:
###### Type

Type: Boolean.(true|false)>

### logout
> .logout()

```javascript
BandyerChat.logout();
```

`.logout()`

To logout to the current istance of the widget, you can call the .logout() method. The logout() method will unmount the widget component.

##### Returns:
###### Type

Promise.<(void|Error)>

### toggleWidget
> .toggleWidget()

```javascript
BandyerChat.toggleWidget();
```

`.toggleWidget()`

Toggles the widget from open to close view or viceversa.

##### Returns:
###### Type

Type: Boolean.(true|false)>

### openWidget
> .openWidget()

```javascript
BandyerChat.openWidget();
```

`.openWidget()`

Opens the widget.

##### Returns:
###### Type

Type: Boolean.(true|false)>

### closeWidget
> .closeWidget()

```javascript
BandyerChat.closeWidget();
```

`.closeWidget()`

Closes the widget.

##### Returns:
###### Type

Type: Boolean.(true|false)>

### getLastMessageReceived
> .getLastMessageReceived()

```javascript
BandyerChat.getLastMessageReceived();
```

`.getLastMessageReceived()`

Get the last message received by the widget. 

##### Returns:
###### Type

| Key | Type | Description |
| --------- | :----------: | ----------- |
| id | String | Unique identifier of the message |
| chat | String | Unique identifier of the chat |
| participants | Array | Array of participants |
| text | String | Text of the message |
| timestamp | Date | When message was created |
| sender | String | User alias of the creator of the message |

### getLastMessageSent
> .getLastMessageSent()

```javascript
BandyerChat.getLastMessageSent();
```

`.getLastMessageSent()`

Get the last message sent by the widget. 

##### Returns:
###### Type

| Key | Type | Description |
| --------- | :----------: | ----------- |
| id | String | Unique identifier of the message |
| chat | String | Unique identifier of the chat |
| participants | Array | Array of participants |
| text | String | Text of the message |
| timestamp | Date | When message was created |
| sender | String | User alias of the creator of the message |

### getUser
> .getUser(userAlias)

```javascript
BandyerChat.getUser(userAlias);
```

`.getUser(userAlias)`

Get info e status about the user selected. 

##### Returns:
###### Type

| Key | Type | Description |
| --------- | :----------: | ----------- |
| user.userAlias | String | User alias of the user |
| user.firstName | String | Firstname of the user |
| user.lastName | String |Lastname of the user |
| user.email | String | Email of the user |
| user.image | String | Image of the user |
| user.role | Number | Role of the user |
| status | String | Current status (online, offline, busy) |


### Screen sharing

From the 1.1.0 and newer version the widget can publish a stream that uses a video view of your screen (instead of a camera) as the source. A client connected to the widget can subscribe to the stream (and view it), just as they would subscribe to a stream that uses a camera as the source.

In Chrome, to publish a screen-sharing video, the client needs to add an extension that enables publishing screen-sharing streams for your domain.
As of Firefox 52, an extension (or whitelist listing) is no longer needed for screen sharing. Firefox prompts the end user for access to a screen, window, or application, as it would for access to the camera. For more information, see this Mozilla blog post.

**In all browsers, publishing a screen-sharing stream requires the page to be loaded over HTTPS.**

#### Set url for extension install

The method `BandyerChat.setExtensionUrl('URL_CHROME_WEBSTORE')` is used to redirect the user to the installation page in the chrome web store. It's important to set the url to enable the user to add the correct extension

`Example: 
BandyerChat.setExtensionUrl('https://chrome.google.com/webstore/detail/your-extension/your-extension-id')`

If the user needs the extensions, the widget will display this alert:

<img src="https://cdn.bandyer.com/sdk/js/resources/screenshots/bandyer-chat-widget-extension-install.png" alt="Drawing" style="height: 300px;"/>

#### Use screen sharing in development

To support screen-sharing in Chrome, you must create a Chrome screen-sharing extension enabled for localhost or any other development domain. Please write an email to <a href="mailto:info@bandyer.com?subject=screen-sharing-widget-development">info@bandyer.com</a> to obtain it.

#### Distributing a screen-sharing extension
In order to use screen-sharing at your website, Chrome users need to install your screen-sharing extension.
You must package your Chrome screen-sharing extension and register it in the Chrome Web Store. See the <a href="https://developer.chrome.com/webstore/publish" target="_blank">Chrome documentation</a> for details on publishing your extension in the Chrome Web Store.