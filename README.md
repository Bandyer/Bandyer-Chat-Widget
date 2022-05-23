# WEB BANDYER SDK

The BandyerSDK is a fast and effective way to offer a live videochat in your web application.

### Consuming a library
You can consume the library from NPM:

`npm install @bandyer/bandyer-chat-widget`

or embed it directly in your HTML getting it from our CDN:

`<script src="https://cdn.bandyer.com/sdk/js/chat/X.X.X/bandyer-widget.min.js"
type="text/javascript" ></script>`


> Example embed in HTML page;

```html
<html>
<head></head>
<body>
<script src="https://cdn.bandyer.com/sdk/js/chat/2.1.2/bandyer-widget.min.js" type="text/javascript" >
</script>
</body>
</html>
```

The script attaches in the window object the global variable **BandyerSDK** from where you can access the library.

<a name="supported_browsers"></a>
#### Supported browsers

| Browser 	          | min version |        Plugin requested        |
|--------------------|:-----------:|:------------------------------:|
| Chrome	           |    72		  |                                |
| Firefox	           |    54		  |                                |
| Safari	           |    12		  |                                |
| Edge new           |    79	     |                                |
| Internet Explorer	 |    11       | Temasys WebRTC Plugin for Call |



#### Versions

The latest version is: 2.1.2
[https://cdn.bandyer.com/sdk/js/chat/2.1.2/bandyer-widget.min.js](https://cdn.bandyer.com/sdk/js/chat/2.1.2/bandyer-widget.min.js)

> if you're upgrading from v1.x.x you can find the migration guide [here](#migration)

For the complete list of versions changes visit: [CHANGELOG](https://github.com/Bandyer/Bandyer-Chat-Widget/blob/gh-pages/CHANGELOG.md)

#### Screenshots
<p>
<img src="https://cdn.bandyer.com/sdk/js/resources/screenshots/bandyer-chat-widget-widget-channels-open-600.jpg" alt="Drawing" height="400" width="240" />
<img src="https://cdn.bandyer.com/sdk/js/resources/screenshots/bandyer-chat-widget-widget-chat-open-600.jpg" alt="Drawing" height="400" width="240"/>
<br>

<img src="https://cdn.bandyer.com/sdk/js/resources/screenshots/bandyer-chat-widget-ringingin-600.jpg" alt="Drawing" height="300" width="270"/>
<img src="https://cdn.bandyer.com/sdk/js/resources/screenshots/bandyer-chat-widget-callout-600.jpg" alt="Drawing" height="300" width="270" />
<br>

<img src="https://cdn.bandyer.com/sdk/js/resources/screenshots/bandyer-chat-widget-widget-call-600.jpg" alt="Drawing" height="300" width="320" />
<img src="https://cdn.bandyer.com/sdk/js/resources/screenshots/bandyer-chat-widget-widget-gear-open-600.jpg" alt="Drawing" height="300"  width="320"/>
</p>

## BandyerSDK

### Methods

* [configure](#configure)
* [destroyClient](#destroy-client)

### Properties


| Name         |               Type                | Description                                                        |
|--------------|:---------------------------------:|--------------------------------------------------------------------|
| version | string | Return the current version of the widget                              |


<a name="configure"></a>
### Configure
> .configure(config)

```javascript
const Client: Client = await BandyerSDK.configure({
  appId: 'client secret',
  region: 'eu or in',
  environment: 'sandbox or production',
});

```

This method allows the configuration of the BandyerSDK and it returns a [Client](#client) object that can be used to connect and use the library.
Be sure to keep a reference of this object somewhere in your code because it is impossible to retrieve it again due to security constraints.

The configuration of a new BandyerSDK instance is made by calling the `BandyerSDK.configure()` method. The available options are the following:

##### Parameters

| Parameter            | Required |        Default         | Description                                                                                                                                                                                   |
|----------------------|:--------:|:----------------------:|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| region               |   yes    |                        | Region on witch your account belongs. Allowed parameters are `eu`, `in` or `us`                                                                                                                |
| environment          |   yes    |                        | Allowed values are: `sandbox` or `production`                                                                                                                                                 |
| appId                |   yes    |                        | A valid appId associated to your account                                                                                                                                                      |
| hidden               |    no    |         false          | Configure the widget to start in hidden mode (not visible in the HTML)                                                                                                                        |
| layout               |    no    |     default layout     | Specify the custom layout (see more [here](#custom-layout))                                                                                                                                   |
| recordingType        |    no    |         'none'         | Wether the recording is disable (none) or starts automatically at the beginning of a call(automatic) or must be started manually(manual). Allowed values are: `none`, `manual` or `automatic` |
| isAdmin              |    no    |         false          | Specify wether the logged user is admin of the calls initiated from the widget. Admin users are able to start/stop the recording when is manual                                               |
| callType             |    no    |      audio\_video      | Specify the call type. Allowed values are: `audio_only`, `audio_upgradable`, `audio_video`                                                                                                    |
| mode                 |    no    |         embed          | Specify the widget call mode. Allowed values are: `embed` or `window`                                                                                                                         |
| language             |    no    |          'en'          | Specify the language of the widget Allowed values are: `en` or `it`                                                                                                                           |
| userDetailsProvider  |    no    | default user provider  | Specify the data for each user (see more [here](#userdetailsprovider))                                                                                                                        |
| userDetailsFormatter |    no    | default user formatter | Specify how user data is formatted in the UI  (see more [here](#userdetailsformatter))                                                                                                        |
| tools                |    no    |   All tools disabled   | Specify the tools to enable during the call (embed and window mode)(See more [here](#tools-option))                                                                                           |
| virtualBackground    |    no    |         false          | It allows to publish the local webcam with blurred or the replaced background by default (embed and window mode). Allowed values are: `blur` or `image`                                       |
| feedback             |    no    |         false          | Specify wether to show the view to leave a feedback at the end of the call                                                                                                                    |


##### Errors

| Name                  | description                                                                          |
|-----------------------|--------------------------------------------------------------------------------------|
|client\_already\_exists | A client exists already, you need to destroy the existing client before creating a new one |
| invalid\_config\_error  | One or more parameters have an incorrect type. See the message to know which ones |
| browser\_not\_supported | The current browser is not supported, please check the compatibility [table](#supported_browsers)             |


#### Call type options:

- `audio_only`: the call is only audio and the participants can't use the webcam
- `audio_upgradable`: the call begins with only audio but the participants are allowed to enable the video later during the call
- `audio_video`: the call begins with audio and video enabled

#### Mode options:

- `embed`: the call is shown in the widget view
- `window`: the call is shown in a separated popup window


#### Hidden options

The widget remains not visible until it receives the following events:

1. addChat event
2. incoming call event


<a name="tools-option"></a>
#### Tools option

By default, if no tools are provided (missing field), all the tools are disabled.

#### List of available tools

| Name |      Mode      |                                              Description                                               |
|------|:--------------:|:------------------------------------------------------------------------------------------------------:|
| chat |     Window & Embed    |                           Specify wether to initialize the chat module or not                          |
| screen\_sharing | Window & Embed |                                   Enable the screen\_sharing feature                                   |
| file\_upload   | Window & Embed |                                   Enable the capability to send file                                   |
| whiteboard    |     Window     |   If true enable all the whiteboard tools. Can be an object of [whiteboard tools](#whiteboard-tools)   |
| snapshot      |     Window     |                                      Enable the snapshot feature                                       |
| live\_edit     |     Window     |                                     Enable the live\_edit feature                                      |
| live\_pointer  |     Window     |           Enable to send pointer-events to others participants (always active in reception)            |

The whiteboard(WB), snapshot(SN) and live_edit(LE) tools are strictly correlated, so use it accordingly as follows:

| Combination                              | Receive live\_edit | Collaborate | Snapshot & Gallery | Open whiteboard |
|------------------------------------------|:-----------------:|:-----------:|:------------------:|:---------------:|
| SN+ LE + WB                              |         ✅         |      ✅      |         ✅          |        ✅        |
| SN                                       |         ❌         |      ❌      |         ✅          |        ❌        |
| SN + WB (default LE active in reception) |         ✅         |      ❌      |         ✅          |        ✅        |
| WB (default LE active in reception)      |         ✅         |      ❌      |         ❌          |        ✅        |
| NONE                                     |         ❌         |      ❌      |         ❌          |        ❌        |

<a name="whiteboard-tools"></a>
#### Whiteboard tools

```json
{
  "tools": {
    "whiteboard": {
      "wb_add_file": true,
      "wb_cursor": true,
      "wb_text": true,
      "wb_shape": true,
      "wb_pen": true,
      "wb_eraser" : true
    }
  }
}
```

The whiteboard tools object is included in the tools parameter

| Name        |                        Description                         |
|-------------|:----------------------------------------------------------:|
| wb\_add\_file |           Allows to add files on the whiteboard            |
| wb\_cursor   | Allows to send the cursor events to the other participants |
| wb\_text     |            Allows to add text on the whiteboard            |
| wb\_shape    |           Allows to add shape on the whiteboard            |
| wb\_pen      |         Allows to using the pen on the whiteboard          |
| wb\_eraser   |     Allows to erase a previous draw on the whiteboard      |



<a name="custom-layout"></a>
#### Custom layout

The widget has custom configurable layout to give the opportunity to match the look and feel you prefer.
The layout option is composed by a list of other keys. The table above is the list of the available options:


| Key             |                         Options                         | Description                                               |
|-----------------|:-------------------------------------------------------:|-----------------------------------------------------------|
| header          |                    background, color                    | Specify the background and color of the header            |
| headerButton    |                    background, color                    | Specify the background and color of the header buttons    |
| body            |                    background, color                    | Specify the background and color of the body              |
| launcher        |                       background                        | Specify the background of the launcher                    |
| messageSent     |                    background, color                    | Specify the background and color of the messages you sent |
| messageReceived |                    background, color                    | Specify the background and color messages you received    |
| dial            |                    background, color                    | Specify the background and color of the dial view         |
| call            |                   background,  color                    | Specify the background and color of the call view         |
| feedback        | body: {background, color}, buttons: {background, color} | Specify the theme for the feedback view                   |
| fontFamily      |                       font Family                       | Font family of the entire widget                          |

Here an example:

```javascript
BandyerSDK.configure({
  region: 'eu',
  appId: 'wAppId_fake123456',
  environment: 'sandbox',
  layout: {
    body: {background: '#0069B4', color: '#000'},
    dial:{background: '#003762', color: '#fff'},
    call: {background: '#003762', color: '#fff'},
    messageSent: {background: '#003762', color: '#fff'},
    launcher: {background: '#0069B4'},
    header: {background: '#003762', color: '#fff'},
    headerButton: {background: '#0069B4', color: '#fff'},
    feedback: {body: {background: '#0069B4', color: '#fff'}, buttons: {background: '#0069B4', color: '#fff'}},
    fontFamily: '"Segoe UI","Segoe",Tahoma,Helvetica,Arial,sans-serif'
  }
})
```

<a name="userdetailsprovider"></a>
#### userDetailsProvider

The widget has a custom configurable function that allows customizing the users' information, which later will be displayed in the UI.

The userDetailsProvider is optional, but if defined must be a function.

This function takes an array of String (userId) as the only input parameter and must return a Promise that contains an Array of objects, one object for each userId provided as input.

**Performance considerations**
The userDetailsProvider function is called and waited internally for up to 1200 ms, otherwise it uses the default provider logic.
For this reason your logic will be applied only if it is faster than 1200 ms.

Every single object representing a user and must contain a userId key(otherwise the object will be ignored) and optionally other keys that can be used to define the logic used in your custom userDetailFormatter.

Here an example:

```javascript

yourProviderFunction = function (usersIds){
  const userObjPromises = [];
  usersIds.forEach( (userId) => {
    // Your logic here
    const user = yourAsyncFetchFunction(userId);
    // Example of yourAsyncFetchFunction promise return
    /* {
        userId: userId,
        firstName: myFirstName,
        lastName: myLastName,
        image: myImage
    }; */
    usersObjPromises.push(user);
  });
  return Promise.all(userObjPromises);
}

BandyerSDK.configure({
  region: 'eu',
  appId: 'wAppId_fake123456',
  environment: 'sandbox',
  userDetailsProvider: yourProviderFunction
})
```
N.B define a userDetailsProvider without the relative userDetailsFormatter is useless since the displayed result will be the userId as it is the default logic of userDetailsFormatter.

<a name="userdetailsformatter"></a>
#### userDetailsFormatter

The widget has a custom configurable function that lets you customize how users name are displayed in the UI.
The userDetailsFoxrmatter is optional, but if defined, it must be a function.

This function takes as input parameter an Object that represents one user and must return a String that represents how the user identity must be displayed in the UI.

If the return value is not a String or the logic fails, the displayed information will be the userId.

Here an example:

```javascript

yourFormatterFunction = function (user){
  return user.firstName + " " + user.lastName;
}

BandyerSDK.configure({
  region: 'eu',
  appId: 'wAppId_fake123456',
  environment: 'sandbox',
  userDetailsFormatter: yourFormatterFunction
})
```
N.B define a userDetailsFormatter without the relative userDetailsProvider can be useless since the displayed result will use the information provided at user creation.





<a name="destroy-client"></a>
### destroyClient
> .destroyClient()

```javascript
await BandyerSDK.destroyClient();

```

Allows to de-initialize the BandyerSDK, this operation destroys the client reference after which you are able to configure a new Client.

<a name="client"></a>
## Client type

### Methods

* [connect](#connect)
* [disconnect](#disconnect)
* [updateAccessToken](#update-token)
* [addChannel](#add-channel)
* [removeChannel](#remove-channel)
* [getChannelView](#get-channel-view)
* [selectChannelsView](#select-channels-view)
* [createCall](#create-call)
* [joinCallURL](#join-call-url)
* [getOnlineUsers](#get-online-users)
* [showWidget](#show-widget)
* [hideWidget](#hide-widget)
* [openWidget](#open-widget)
* [toggleWidget](#toggle-widget)
* [closeWidget](#close-widget)



### Properties

| Name         |               Type                | Description                                                        |
|--------------|:---------------------------------:|--------------------------------------------------------------------|
| channelsView | [channelView](#channel-view) | Retrieve the list of channel view                                  |
| callView     |    [CallView](#call-view)    | Retrieve the current callView                                      |
| region       |              string               | Retrieve the region value forwarded in the configuration step      |
| environment  |              string               | Retrieve the environment value forwarded in the configuration step |
| appId        |              string               | Retrieve the appId value forwarded in the configuration step       |
| userId       |              string               | Retrieve the userId value forwarded in the configuration step      |




### Events

| Name         					| Description                                                        |
|--------------------------- 	|--------------------------------------------------------------------|
| client:access_token:expired	|	The session expired, for some reason the update token process is failed, you need to re-connect the Client with a new access token|
| client:access\_token:about\_to\_expire| The session is about to expire, you need to provide a valid accesstoken through the [updateAccessToken](#update-token) api|
| client:force\_disconnect |The user was disabled or deleted via REST api |
| channel:message:sent 			| When a message was sent in a channel                             |
| channel:message:received   	| When a message was received in a channel                       |
| channel:added       | When a channel was added using client api or rest       |
| channel:removed  |  When a channel was removed using client api or rest |
| call:incoming        | When there is an incoming call       |
| call:status:changed       | Triggered when the call change the status. See [call status](#call-status)   |
|user:status:changed| Triggered when a user change the status(online / offline) |


<a name="client-life-cycle"></a>
### Client life cycle


To connect the Client object you need a valid accessToken, you can obtain a valid access token via [rest API](https://docs.bandyer.com/Bandyer-RESTAPI/#generate-credentials)

In order to maintain the connected state you need to bind two events to the Client object(obtained with [Configure](#Configure)):
- access\_token\_is\_about\_to\_expire
- access\_token\_expired
  Follow an example of licfecycle implementation:


```javascript

//configuration step

// access token request

Client.on('client:access_token:is_about_to_expire', async (data) => { // data: {expiresAt: "2022-01-10T11:41:19.000Z"'}
  const accessToken = await yourAsyncFunction(); // async function that allow you to ask a new accessToken to the server
  // Provide the obtained accessToken to the sdk
  const { expiresAt } = await Client.updateAccessToken(accessToken); // return the new expiration date

})
Client.on('client:access_token:expired', async() => {
  // the session expired, for some reason the update token process is failed, you need to re-connect the Client with a new access token
  await Client.disconnect();
  // retrieve a new accessToken
  await Client.connect(userId, accessToken)
})

Client.on('client:force_disconnect', () => {
  // the user was disabled or deleted from a rest api
})
try {
  await Client.connect(userId, accessToken);
} catch (e) {
  console.error('Fail to connect the client', error)
}


```

<a name="connect"></a>
#### Connect

To connect the Client object you need a valid accessToken, you can obtain a valid access token via [rest API](https://docs.bandyer.com/Bandyer-RESTAPI/#generate-credentials)

The access token must match the userId provided


> .connect()


```
try {
    await Client.connect(userId, accessToken);
} catch (e) {
    console.error('Fail to connect the client', error)
}


```

##### Parameters


| Parameter   | Required | Default | Description                                     |
|-------------|:--------:|:-------:|-------------------------------------------------|
| userId      |   yes    |         | User that you want to authenticate              |
| accessToken |   yes    |         | Access token corresponding to the user provided |

##### Errors

| Name                           | description                                                                          |
|--------------------------------|--------------------------------------------------------------------------------------|
| sdk\_version\_invalid            | If one or more parameter have an incorrect type, see the message to knows which ones |
| sdk\_version\_unsupported        | The browser is not supported, please check the compatibility table above             |
| app\_id\_invalid                 | The appId used in configuration step is invalid                                      |
| access\_token\_expired           | The access token is expired, please retrieve a new one before retry the connection   |
| access\_token\_invalid           | he access token is invalid, please check the token generation                        |
| access\_token\_invalid\_signature | The access token is compromised, please check the token generation                   |
| access\_token\_invalid\_user      | The access token not belong to the userId forwarded in the connect method            |
| user\_not\_found                 | The user does not exists                                                             |

#### Disconnect

<a name="disconnect"></a>
> .disconnect()

```javascript
 await Client.disconnect();

```

#### Update access token
<a name="update-token"></a>

Allow to refresh the session, you can obtain a valid access token via [rest API](https://docs.bandyer.com/Bandyer-RESTAPI/#generate-credentials)

> .updateAccessToken()

```javascript
 await updateAccessToken(accessToken);

```

##### Parameters

| Parameter   | Required | Default | Description                                     |
|-------------|:--------:|:-------:|-------------------------------------------------|
| accessToken |   yes    |         | Access token corresponding to the user provided |

##### Errors

| Name                           | description                                                                          |
|--------------------------------|--------------------------------------------------------------------------------------|
| access\_token\_expired           | The access token is expired, please retrieve a new one before retry the connection   |
| access\_token\_invalid           | he access token is invalid, please check the token generation                        |
| access\_token\_invalid\_signature | The access token is compromised, please check the token generation                   |
| access\_token\_invalid\_user      | The access token not belong to the userId forwarded in the connect method            |


### Client: Chat API and types

If the Client was created with the chat module enabled it can perform some chat operation, also expose some real time events.

#### Events

```javascript

// when a message was sent in a channel
Client.on('channel:message:sent', ({message: Message}) => {
  // your logic
})

// when a message was received in a channel
Client.on('channel:message:received', ({message: Message}) => {
  // your logic
})


// when a channel was added using api/ rest 
Client.on('channel:added', ({channel: Channel}) => {
  // your logic
})

// when a channel was removed using api/ rest 
Client.on('channel:removed', ({channelId: string, participants: string[] }) => {
  // your logic
})
```

<a name="add-channel"></a>
#### Add channel


To create a chat channel another user of your platform, you need to call the .addChannel() method.
The addChannel method expect a valid user alias (it must be a user already created). Once the method is called, the widget will return a [channelView](#channel-view)

> .addChannel(userId)

```javascript
const channelView: channelView = await Client.addChannel('usr_fr55ga3');
```




##### Parameters

| Name      |  Type  | Description                     |
|-----------|:------:|---------------------------------|
| userId | String | User that you want to chat with |

##### Errors

| Name                 | description                                                                                |
|----------------------|--------------------------------------------------------------------------------------------|
| validation\_error     | One of the arguments is invalid or the chat module is not initialized                      |
| authentication\_error | The Client is not authenticated                                                            |
| create\_channel\_oto   | An error has occurred during the creation phase, please refer to the message in the error  |


<a name="remove-channel"></a>
#### Remove channel

To remove a chat channel you need to call the .removeChannel() method.
The removeChannel will remove the chat between the user authenticated and the user specified as input of the method.
All the messages between them will be deleted permanently.

> .removeChannel(userId)

```javascript
await Client.removeChannel('usr_fr55ga3');
```

##### Parameters

| Name      |  Type  | Description                                            |
|-----------|:------:|--------------------------------------------------------|
| userId | String | Other participants of the chat that you want to remove |

##### Errors

| Name                 | description                                                                              |
|----------------------|------------------------------------------------------------------------------------------|
| validation\_error     | One of the arguments is invalid or the chat module is not initialized                    |
| authentication\_error | The Client is not authenticated                                                          |
| delete\_channel       | An error has occurred during the remove phase, please refer to the message in the error  |

<a name="get-channel-view"></a>
#### Get channel view

Allow to retrieve a specific [channel view](#channel-view) with a user

> ..getChannelView(userId)

```javascript
Client. getChannelView(userId);
```

##### Parameters

| Name      |  Type  | Description                                            |
|-----------|:------:|--------------------------------------------------------|
| userId | String | Other participants of the chat that you want to remove |

##### Errors

| Name                 | description                                                                              |
|----------------------|------------------------------------------------------------------------------------------|
| validation\_error     | One of the arguments is invalid or the chat module is not initialized |
| channel\_not\_found| The channel does not exists                                               |


<a name="select-channels-view"></a>
#### Select channels view

Allow to show the main view of the Client, if you are in a call view or in a channel view this method allow to change the current view to the list of channels


> .selectChannelsView()

```javascript
Client.selectChannelsView();
```


### Client: Call API and types

The client expose apis and events in order to manage a call lifecycle

#### Events

```javascript
// triggered when a call is created (status equal to dialing)
Client.on('call:incoming', (call: Call) => {
  // yuor logic 
});

// triggered when the call change the status (connecting, connected, ended)
Client.on('call:status:changed', (call: Call, status) => {
  // yuor logic, note if the status was ended, the call object can have a endReason
});
```

<a name="create-call"></a>
#### Create call

> .createCall(users, options)

Create a call with arbitrary call options with the users specified in the array (Only one user at the moment)

This method return a [callView](#call-view) that is a UI representation of the call, this object contains also the call(logical)

```javascript
const callView: CallView = Client.createCall(['usr_fr55ga3'], {'call_type':'audio_video'});
```

**Note:** If the widget is in hidden mode, the createCall method mode will display the widget.

##### Parameters

| Name         |   Type   | Description                                                                  |
|--------------|:--------:|------------------------------------------------------------------------------|
| participants | string[] | List of users with whom you want to start a call (at most one at the moment) |
| options      |  Object  | Call options                                                                 |

##### Options

| Name          | Default                 |  Type   | Description                                                 |
|---------------|-------------------------|:-------:|-------------------------------------------------------------|
| callType      | inherit from the config | string  | Can be 'audio\_only', 'audio\_upgradable', 'audio\_video'      |
| recording     | inherit from the config | boolean | Allow to define if the call start with recording            |
| recordingType | inherit from the config | string  | Can be 'manual' or 'automatic'                              |
| isAdmin       | inherit from the config | boolean | Allow the user to control the manual recording capabilities |

N.B. if the call is {recording: true, recordingType: 'manual', isAdmin: false} create a call with the recording capability but no-one is able to start the recording.
In order to do that create this type of call with isAdmin: true

#### Errors
| Name                       | description                                                                   |
|----------------------------|-------------------------------------------------------------------------------|
| validation\_error           | One of the arguments is invalid                                               |
| another\_call\_in\_progress   | The user is already in call                                                   |
| current\_user\_not\_available | The connected user is in disconnection phase                                  |
| current\_user\_busy          | The connect user is busy on another device                                    |
| all\_users\_busy             | All the users are busy                                                        |
| no\_plus\_user               | Should be at least one plus user in the call                                  |
| room\_create\_error          | A generic error has occurred please check the error message to know the cause |
| internal\_server\_error      | A server problem is occurred please retry or contact for support              |

<a name="join-call-url"></a>
#### Join call URL

> .joinCallURL(url)

Join a call URL retrieved from the rest api integration Documentation can be found [here](https://docs.bandyer.com/Bandyer-RESTAPI/#create-a-room)

This method return a [callView](#call-view) that is a UI representation of the call, this object contains also the call(logical)

```javascript
const call: CallView = Client.joinCallUrl('https://sandbox.bandyer.com/region/direct-rest-call-handler/token');
```

**Note:** If the widget is in hidden mode, the joinCallURL method mode will display the widget.
**Note:** The widget must be authenticated and the url must be coupled with the user authenticated on the widget.

##### Parameters

| Name    |  Type  | Description            |
|---------|:------:|------------------------|
| url     | string | Valid url for the call |

#### Errors
| Name                        | description                                                                   |
|-----------------------------|-------------------------------------------------------------------------------|
| validation\_error            | One of the arguments is invalid                                               |
| another\_call\_in\_progress    | The user is already in call                                                   |
| current\_user\_not\_available  | The connected user is in disconnection phase                                  |
| current\_user\_busy           | The connect user is busy on another device                                    |
| all\_users\_busy              | All the users are busy                                                        |
| invalid\_url                 | The given URL is invalid                                                      |
| invalid\_token               | The call token is invalid or disabled                                         |
| user\_not\_associated\_to\_link | The user does not belong to the link                                          |
| join\_url\_mtm                | At the moment the client does not support the many to many calls              |
| no\_plus\_user                | Should be at least one plus user in the call                                  |
| room\_create\_error           | A generic error has occurred please check the error message to know the cause |
| internal\_server\_error       | A server problem is occurred please retry or contact for support              |



### Client : User API and events

The client expose apis and events to keep track of the other users status and life cycle

#### Events:

```javascript
// triggered when a user in you company change you status(online, offline)
Client.on('user:status:changed', (data: { userId: string, status: string}) => {
  // yuor logic 
});
```


| Name                  | description                                                                       |
|-----------------------|-----------------------------------------------------------------------------------|
| invalid\_call\_status   | The call cannot be already in an ended status                                     |
| user\_not\_in\_dialing   | The other participants is in disconnection phase                                  |
| dial\_stop\_error       | Generic dial stop error, please refer to the message in order to know the cause   |
| dial\_decline\_error    | Generic dial stop error, please refer to the message in order to know the cause   |
| internal\_server\_error | A server problem is occurred please retry or contact for support                  |

<a name="get-online-users"></a>
#### getOnlineUsers


> .getOnlineUsers()

Allow to retrieve the current list of online users


```javascript
const users: string[] = Client.getOnlineUsers()
```


### Client : UI API

<a name="show-widget"></a>
#### Show widget

> .showWidget()

Allow to render the UI component when the Client was created with hidden:true


```javascript
Client.showWidget()
```

<a name="hide-widget"></a>
#### Hide widget

> .hideWidget()

Allow to remove the UI component when the Client was created with hidden:false


```javascript
Client.hideWIdget()
```

<a name="open-widget"></a>
#### Open widget

> .openWidget()

Allow to expand the widget component


```javascript
Client.openWidget()
```
<a name="close-widget"></a>
#### Close widget

> .closeWidget()

Allow to minimize the widget component


```javascript
Client.closeWidget()
```

<a name="toggle-widget"></a>
#### Toggle widget

> .toggleWidget()

Allow expanding or minimize  the widget component based on the status


```javascript
Client.toggleWidget()
```


<a name="channel-view"></a>
## Channel view type

A channel view type is a UI representation of the logical [Channel](#channel-type).
On this object you can perform all the UI api's

### Methods

* [select](#channel-view-select)

### Property:

| Name     |           Type           | Description                                               |
|----------|:------------------------:|-----------------------------------------------------------|
| textArea |          String          | Allow to get and set the textArea field on the channel UI |
| channel  | [Channel](#channel-type) | Retrieve the logical channel                              |


#### Select
<a name="channel-view-select"></a>
> .select()

This method allow to change the currentView to the channel one

```javascript

// channelView received from an event or retrieved from the channelView() method

channelView.select();
```

<a name="channel-type"></a>
## Channel type

A channel is a logical representation of the chat
On this object you can perform all the logical operation like retrieve messages, send message, get unreadMessages and participants


### Methods

* [fetchMessages](#fetch-messages)
* [sendMessage](#send-message)

### Property

| Name           |            Type            | Description                                                        |
|----------------|:--------------------------:|--------------------------------------------------------------------|
| channelId      |           String           | Retrieve the unique channelId, it can be use also in our rest apis |
| participants   |          String[]          | Retrieve the userIds of the participants                           |
| unreadMessages |           number           | Retrieve the count of the unread messages                          |
| messages       | [Message](#message-type)[] | Array of messages in the channel                                   |

### Events

| Name 					| Description |
| -------------------- | ----------|
| channel:message:added| Notify when in the current channel a message (sent or received) was added |

```javascript

Channel.on('channel:message:added', (message: Message) => {
  // your logic
})
```

#### Fetch messages
<a name="fetch-message"></a>
> .fetchMessages(messageToFetch, anchor, direction)


This method allow to retrieve the channel messages programmatically

```javascript

// channelView received from an event or retrieved from the channelView() method

const messagesObejct:{ messages: Message[], anchor: string } = channelView.fetchMessages(messageToFetch, anchor, direction)
```

##### Parameters

| Name           |   Type   | Description                                                           |
|----------------|:--------:|-----------------------------------------------------------------------|
| messageToFetch |  number  | Number of messages to fetch                                           |
| anchor         | String[] | Starting messageId from witch start to fetch                          |
| direction      |  string  | Use 'backwards' to retrieve past messages , use 'afterward' otherwise |

##### Errors

| Name                 | description                                                 |
|----------------------|-------------------------------------------------------------|
| channel\_not\_exists   | When the request is performed after the channel was deleted |
| message\_anchor\_error | Invalid anchor                                              |


#### Send message
<a name="send-message"></a>
> .sendMessage(message)


This method allow to send a message programmatically



```javascript

// channelView received from an event or retrieved from the channelView() method

const message: Message = channelView.sendMessage(text)
```

##### Parameters

| Name      |   Type   | Description                                                           |
|-----------|:--------:|-----------------------------------------------------------------------|
| message   |  string  | text message that you want to send                                    |

##### Errors

| Name               | description                                                 |
|--------------------|-------------------------------------------------------------|
| channel\_not\_exists | When the request is performed after the channel was deleted |
| message\_not\_saved  | Error in storing the message, please retry                  |


<a name="message-type"></a>
## Message type

A message is a logical representation of a single message in a [Channel](#channel-type)

### Property

| Name         |           Type           | Description                      |
|--------------|:------------------------:|----------------------------------|
| messageId    |          String          | Retrieve the unique messageId    |
| channel      | [Channel](#channel-type) | Retrieve the logical channel     |
| sender       |          string          | UserId of the sender             |
| text         |          String          | Text of the message              |
| creationDate |       String(ISO)        | ISO Date of the message creation |

<a name="call-view"></a>
## Call view type

A call view type is a UI representation of the logical [Call](#call-type).
On this object you can perform all the UI operation

### Methods

* [select](#call-view-select)

### Property

| Name    |         Type          | Description                        |
|---------|:---------------------:|------------------------------------|
| call    |    [Call](#call-type) | Allow to retrieve the logical call |


#### Select

<a name="call-view-select"></a>
> .select()

This method allow to change the currentView to the call one

```javascript

// callView received from an event or retrieved from the callView getter on the client object

callView.select();
```
<a name="call-type"></a>
## Call type

A call is a logical representation of the room created
On this object you can perform all the logical operation like answer, end, get status, participants, options etc

### Methods

* [answer](#answer)
* [end](#end)

<a name="call-status"></a>
### Properties

| Name           |      Type      | Description                                                                                                                      |
|----------------|:--------------:|----------------------------------------------------------------------------------------------------------------------------------|
| roomId         |     String     | RoomId of the call, can be used in out rest api to retrieve information                                                          |
| options        |     Object     | Contains call information about his initialization and status                                                                    |
| creationDate   |  string(ISO)   | Creation date of the call                                                                                                        |
| participants   |    string[]    | Array of userId that participate to the call                                                                                     |
| direction      |     string     | 'incoming' or 'outgoing'                                                                                                         |
| status         |     string     | can be 'dialing', 'connecting' 'connected' or 'ended'                                                                            |
| recordingState | String  | 'started' if the recording was started, 'stopped' otherwise |
| endReason      | string or null | Filled if the call is in the end state, should be 'declined', 'canceled', 'answered\_of\_another\_device', 'hang\_up', 'timeout' | 


#### Options object
| Name            |  Type   | Description                                                 |
|-----------------|:-------:|-------------------------------------------------------------|
| callType        | String  | Can be 'audio\_video', 'audio\_upgradable', 'audio\_only'   |
| recordingType   | String  | Can be 'none', 'automatic' or 'manual'                      |
| live            | String  | If the call trigger the incoming call event or hook         |



### Events

| Name                    | Description                               |
|-------------------------|-------------------------------------------|
| status:changed          | Triggered  when a call change his status  |
| recording:state:changed | Triggered  when the recordingState change |

A call have some events that allow to retrieve real time information

```javascript

// Triggered  when a call change his status
Call.on('status:changed', (status: string) => {
  // your logic
  
})

// Triggered  when the recording state was changed
Call.on('recording:state:changed', ({ recordingState: string }) => {
// your logic
})
```

<a name="answer"></a>
#### Answer

> .answer()


This method allow to answer an incoming call in dialing state

```javascript

// call received from an event or retrieved from the callView.call getter

await call.answer()
```

##### Errors

| Name                  | description                                                                                       |
|-----------------------|---------------------------------------------------------------------------------------------------|
| invalid\_call\_status   | In order to answer a call, this one should have an incoming direction an must be in dialing state |
| callee\_not\_available  | The other participants is in disconnection phase                                                  |
| dial\_answer\_error     | Generic error, please refer to the message in order to know the cause                             |
| internal\_server\_error | A server problem is occurred please retry or contact for support                                  |


<a name="end"></a>
#### End
> .end()


This method allow to end a call

It automatically performs the correct behaviour(decline, cancel or hangUp) based on the call status

```javascript

// call received from an event or retrieved from the callView.call getter

await call.end()
```
<a id="migration"> </a>
# Migration from v1.x.x to v2.x.x

## Library changes

The library name has been changed from `BandyerChat` to `BandyerSDK` so now you can find the library once loaded from the CDN in `window.BandyerSDk`.

### Initialize the BandyerSDK

The `BandyerChat.create()` function has been renamed to `BandyerSDK.configure()` to better represent its purpose.

The `BandyerSDK.configure()` function will now return a `client` which exposes all the apis previosuly exposed on the `BandyerChat` object.

The `client` object will also expose a new distinct `client.connect()` function that connects the SDK.

The `BandyerChat.logout()` function has been replaced by the `client.disconnect()` function exposed on the `client` object and by the `BandyerSDK.destroyClient()` that can be used to reconfigure the SDK.

### Migrate BandyerChat.create to BandyerSDK.configure

```javascript

console.log(BandyerChat.version());

const client = await BandyerChat.create({ userAlias, environment, appId, mode, layout});

// the SDK is connected
// put here your logic

await BandyerChat.logout();

```

becomes

```javascript

console.log(BandyerSDK.version);

const client = BandyerSDK.configure({ region, environment, appId, mode, layout, tools });

// note that the client is not globally expose, if you want you can global store the object with window.bandyerClient =client

client.on('client:access_token:is_about_to_expire', async () => {
  const accessToken = await getAccessToken(userId); // your async function to obtain a valid accessToken 
  await client.updateAccessToken(accessToken);
})

// the SDK is configured

// your async function to obtain a valid accessToken 
const accessToken = await getAccessToken(userId);

// userAlias parameters is now called userId
await client.connect(userId, accessToken);

// the SDK is connected
// put here your logic

await client.disconnect(); // replacement of the old BandyerChat.logout() function

BandyerSDK.destroyClient(); // destroys the client allowing a new configuration

```

## Configuration parameters changes

| old value  | new value     | change                                      |
| --------- |---------------|------------------------------------------------|
| record    | recordingType | Parameter key                                         | 
| tools | tools         | Not specifying tools now means that the user will have none|
|language| language      | The current default is `en` |


### Migrate Chat methods

```javascript
const chatsList = await BandyerChat.getChats();

await BandyerChat.addChat(userId);

BandyerChat.selectChat(userId);

BandyerChat.composeMessage(userId, 'How are you?', false);

BandyerChat.composeMessage(userId, 'How are you?', true);

const unreadMessagesList = await BandyerChat.getUnreadMessages();

await BandyerChat.removeChat(userId);

```

becomes

```javascript

const chatsList = Client.channelsView; // array of channelViews instead of getChats()

const channelView = await Client.addChannel(userId);

channelView.select();

channelView.textArea = 'How are you'; // same as composeMessage with send = false

const message = await channelView.channel.sendMessage('How are you'); // same as composeMessage with send = true

channelView.channel.unreadMessages; // get unreadMessages on singleChannels instead of getUnreadMessages()

await Client.removeChannel(userId);

```


### Migrate Chat events

```javascript

Client.on('chat_loaded', callback);
Client.on('message_received', callback);
Client.on('message_sent', callback);

```

becomes

```javascript

// see the documentation in order to know the payload in the callback
Client.on('channel:added', callback); 
Client.on('channel:removed', callback);
Client.on('channel:message:received', callback);
Client.on('channel:message:sent', callback);

```


### Migrate Call methods

```javascript

const call = await BandyerChat.createCall([userId], option);
// const call = await BandyerChat.joinCallUrl(url);
call.hangUp();
```

becomes


```javascript

const callView = await client.createCall([userId], option);
// const callView = await Client.joinCallUrl(url);

callView.call.end(); //take care about the call object changes

```


### Migrate Call events

```javascript

Client.on('incoming_call', (call) => {
    /* call =  {
  		"event": "incoming_call",
  		"callAlias": "room_027b9312e9a5",
  		"callDirection": "outgoing",
  		"callParticipants": ["user1", "user2"],
  		"callOptions": {
    		"record": false,
			"creationDate": "2021-04-13T08:31:03.916Z",
		   "callType": "audio_video", 
    		"live": true
  		}
	}*/
});

Client.on('call_dial_answered',(call) => {
  // your logic
});

Client.on('call_dial_declined',(call) => {
  // your logic
});

Client.on('call_dial_stopped',(call) => {
  // your logic
});

Client.on('call_started',(call) => {
  // your logic
});

Client.on('call_ended',(call) => {
  // your logic
});
```

becomes

```javascript

Client.on('call:incoming', (call: Call) => {

    // call is a calltype object (see documentation to know properties and methods)
  
  call.on('status:changed',(status:string) => {
    // status can be  'dialing', 'connecting' 'connected' or 'ended'
  });
  
  call.answer();
  //call.end();
    
});


Client.on('call:status:changed', (call: Call, status: string) => {

  // call is a calltype object (see documentation to know properties and methods)
  
  // status can be  'dialing', 'connecting' 'connected' or 'ended'
  
  // if the call status is ended the call object have and endReason getter

});


```


### Migrate User methods

```javascript

const user = await BandyerChat.getUser(userId);

console.log(user.status);

const users = await BandyerChat.getUsersStatusList();

users.forEach(user => {
  console.log(user.status);
})

```

becomes

```javascript

const users = Client.getOnlineUsers();

users.forEach(user => {
  console.log('the user', user, 'is online');
})

// if a user is not in the list above the status is offline

```



### Migrate User events

```javascript

Client.on('user_connected', callback);

Client.on('user_disconnect', callback);

```

becomes


```javascript

Client.on('user:status:changed', ({userId, status}) => {
    console.log('the user', userId, 'went', status);
})

```

### Migrate Widget methods


```javascript

BandyerChat.showWidget();
BandyerChat.hideWidget();
BandyerChat.toggleWidget();
BandyerChat.closeWidget();
BandyerChat.openWidget();

```

becomes

```javascript

Client.showWidget();
Client.hideWidget();
Client.toggleWidget();
Client.closeWidget();
Client.openWidget();

```
