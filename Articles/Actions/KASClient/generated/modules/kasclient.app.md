[](../README.md) > [KASClient](../modules/kasclient.md) > [App](../modules/kasclient.app.md)

# Module: App

## Index

### Functions

* [cancelAttachmentDownloadAsync](kasclient.app.md#cancelattachmentdownloadasync)
* [dismissCurrentScreen](kasclient.app.md#dismisscurrentscreen)
* [downloadAttachmentAsync](kasclient.app.md#downloadattachmentasync)
* [generateBase64ThumbnailAsync](kasclient.app.md#generatebase64thumbnailasync)
* [generateUUIDAsync](kasclient.app.md#generateuuidasync)
* [getAppLocaleAsync](kasclient.app.md#getapplocaleasync)
* [getCalendarNameAsync](kasclient.app.md#getcalendarnameasync)
* [getConversationDetailsAsync](kasclient.app.md#getconversationdetailsasync)
* [getCurrentDeviceLocationAsync](kasclient.app.md#getcurrentdevicelocationasync)
* [getCurrentLocale](kasclient.app.md#getcurrentlocale)
* [getDeviceIdAsync](kasclient.app.md#getdeviceidasync)
* [getDeviceLocationAsync](kasclient.app.md#getdevicelocationasync)
* [getFontSizeMultiplierAsync](kasclient.app.md#getfontsizemultiplierasync)
* [getForwardContextAsync](kasclient.app.md#getforwardcontextasync)
* [getIsAppTimeFormat24HoursAsync](kasclient.app.md#getisapptimeformat24hoursasync)
* [getLocalizedStringsAsync](kasclient.app.md#getlocalizedstringsasync)
* [getLocationAddressAsync](kasclient.app.md#getlocationaddressasync)
* [getMapImageAsBase64Async](kasclient.app.md#getmapimageasbase64async)
* [getO365UserDetailsAsync](kasclient.app.md#geto365userdetailsasync)
* [getPackageCustomSettingsAsync](kasclient.app.md#getpackagecustomsettingsasync)
* [getUsersDetailsAsync](kasclient.app.md#getusersdetailsasync)
* [hideProgressBar](kasclient.app.md#hideprogressbar)
* [isAttachmentDownloadingAsync](kasclient.app.md#isattachmentdownloadingasync)
* [isAuthenticationTyepSupportedAsync](kasclient.app.md#isauthenticationtyepsupportedasync)
* [isTalkBackEnabledAsync](kasclient.app.md#istalkbackenabledasync)
* [logToReport](kasclient.app.md#logtoreport)
* [openAttachmentImmersiveView](kasclient.app.md#openattachmentimmersiveview)
* [openImmersiveViewForAttachmentList](kasclient.app.md#openimmersiveviewforattachmentlist)
* [performAuthenticationAsync](kasclient.app.md#performauthenticationasync)
* [performHTTPRequest](kasclient.app.md#performhttprequest)
* [printf](kasclient.app.md#printf)
* [readTalkBackMessage](kasclient.app.md#readtalkbackmessage)
* [registerHardwareBackPressCallback](kasclient.app.md#registerhardwarebackpresscallback)
* [setNativeToolbarProperties](kasclient.app.md#setnativetoolbarproperties)
* [setUserStrings](kasclient.app.md#setuserstrings)
* [showAttachmentPickerAsync](kasclient.app.md#showattachmentpickerasync)
* [showBarcodeScannerAsync](kasclient.app.md#showbarcodescannerasync)
* [showContactPickerAsync](kasclient.app.md#showcontactpickerasync)
* [showDurationPickerAsync](kasclient.app.md#showdurationpickerasync)
* [showImageImmersiveView](kasclient.app.md#showimageimmersiveview)
* [showImagePickerAsync](kasclient.app.md#showimagepickerasync)
* [showLocationOnMap](kasclient.app.md#showlocationonmap)
* [showNativeErrorMessage](kasclient.app.md#shownativeerrormessage)
* [showPlacePickerAsync](kasclient.app.md#showplacepickerasync)
* [showProgressBar](kasclient.app.md#showprogressbar)
* [showQRcodeScannerAsync](kasclient.app.md#showqrcodescannerasync)
* [showUserProfileAsync](kasclient.app.md#showuserprofileasync)
* [startChatAsync](kasclient.app.md#startchatasync)




---

## Functions

<a id="cancelattachmentdownloadasync"></a>

###  cancelAttachmentDownloadAsync

▸ **cancelAttachmentDownloadAsync**(attachment: *[KASAttachment](../classes/kasclient.kasattachment.md)*, callback: *`function`*): `void`


Cancel a download operation queued for an attachment

#### Sample Usage

```
 var attachmentsList = JSON.parse(form.properties[0].value);
 for (var i = 0; i < attachmentsList.length; i++)
 {
      var attachmentItem = attachmentsList[i];
      var attachment = KASClient.KASAttachment.fromJSON(attachmentItem);
      KASClient.App.cancelAttachmentDownloadAsync(attachment);
 }
```


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| attachment | [KASAttachment](../classes/kasclient.kasattachment.md) |  \- |
| callback | `function` |  with error param - error string in case of error; null otherwise |

**Returns:** `void`

___




<a id="dismisscurrentscreen"></a>

###  dismissCurrentScreen

▸ **dismissCurrentScreen**(): `void`


Dismiss the current opened Action's screen (Creation, Response, or Summary)


**Returns:** `void`

___




<a id="downloadattachmentasync"></a>

###  downloadAttachmentAsync

▸ **downloadAttachmentAsync**(attachment: *[KASAttachment](../classes/kasclient.kasattachment.md)*, callback: *`function`*): `void`


Download the attachment specified

#### Sample Usage

```
var imageAttachment =  new KASClient.KASAttachment();
imageAttachment.type = KASClient.KASAttachmentType.Image;
imageAttachment.serverPath = "<server path>";
imageAttachment.fileName = "<file name>";
KASClient.App.downloadAttachmentAsync(imageAttachment, function(downloadedAttachment, error){
     if (!error) {
        console.log(downloadedAttachment); //KASAttachment
     }
});
```


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| attachment | [KASAttachment](../classes/kasclient.kasattachment.md) |  attachment with a valid server path to download |
| callback | `function` |  callback on download completion with below params<br><br>\* @param {KASAttachment} downloadedAttachment the attachment that got downloaded<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="generatebase64thumbnailasync"></a>

###  generateBase64ThumbnailAsync

▸ **generateBase64ThumbnailAsync**(localPath: *`string`*, callback: *`function`*): `void`


Generates Base64 thumbnail for an image whose localPath is given

#### Sample Usage

```
KASClient.App.generateBase64ThumbnailAsync(localPath, function (thumbnail, error) {
    if (error == null && thumbnail != null) {
       //use the thumbnail data and update required dom
     }
});
```


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| localPath | `string` |  localPath for the imageAttachment whose thumbnail needs to be generated |
| callback | `function` |  with below parameters:<br><br>\* @param {string} thumbnail the base64 value<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="generateuuidasync"></a>

###  generateUUIDAsync

▸ **generateUUIDAsync**(callback: *`function`*): `void`


Gets the new UUID

#### Sample Usage

```
 KASClient.App.generateUUIDAsync(function (uuid, error) {
    console.log("generatedUUIDAsync", uuid);
    ...
 });
```


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {string} uuid newly generated uuid<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="getapplocaleasync"></a>

###  getAppLocaleAsync

▸ **getAppLocaleAsync**(callback: *`function`*): `void`


Gets the current app locale, the language in which the app is rendered, useful for localizing MiniApp's strings


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {string} locale can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="getcalendarnameasync"></a>

###  getCalendarNameAsync

▸ **getCalendarNameAsync**(callback: *`function`*): `void`


Gets the current system calendar setting. This is mainly for iOS to identify the calendar name set in phone setting like Gregorian or Japanese or Buddhists.


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {string} calendarName can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="getconversationdetailsasync"></a>

###  getConversationDetailsAsync

▸ **getConversationDetailsAsync**(callback: *`function`*): `void`


Gets conversation related properties


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {KASConversationDetails} result conversation properties<br><br>\* @param {string} error json string for the KASError object containing error code and/or description. |

**Returns:** `void`

___




<a id="getcurrentdevicelocationasync"></a>

###  getCurrentDeviceLocationAsync

▸ **getCurrentDeviceLocationAsync**(callback: *`function`*): `void`


Gets the current device location

#### Sample Usage

```
 KASClient.App.getCurrentDeviceLocationAsync(function (location, error){
     if(error != null) {
          return;
     }
     //use location(KASLocation) as the device location
 });
```


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {string} location can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="getcurrentlocale"></a>

###  getCurrentLocale

▸ **getCurrentLocale**(): `string`

**Returns:** `string`

___




<a id="getdeviceidasync"></a>

###  getDeviceIdAsync

▸ **getDeviceIdAsync**(callback: *`function`*): `void`


Gets deviceId


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {string} deviceId got from integeration service<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="getdevicelocationasync"></a>

###  getDeviceLocationAsync

▸ **getDeviceLocationAsync**(callback: *`function`*): `void`


Gets the previously stored device location


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {string} location can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="getfontsizemultiplierasync"></a>

###  getFontSizeMultiplierAsync

▸ **getFontSizeMultiplierAsync**(callback: *`function`*): `void`


Gets the font size multiplier for large text. Current only required by iOS.


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below params<br><br>\* @param {string} multiplier<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="getforwardcontextasync"></a>

###  getForwardContextAsync

▸ **getForwardContextAsync**(callback: *`function`*): `void`


Gets Forward Context details such as : Card Creation is in forwarded mode


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {Json} returns the Context Details in Json structure |

**Returns:** `void`

___




<a id="getisapptimeformat24hoursasync"></a>

###  getIsAppTimeFormat24HoursAsync

▸ **getIsAppTimeFormat24HoursAsync**(callback: *`function`*): `void`


Gets the current app time format is 24hours or not, the time format selected by user, useful for formatting date time strings properly


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {string} isAppTimeFormat24Hours can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="getlocalizedstringsasync"></a>

###  getLocalizedStringsAsync

▸ **getLocalizedStringsAsync**(callback: *`function`*): `void`


Gets the localized strings' dictionary based on current app locale. Strings must be provided inside the package with names like: strings\_en.json, strings\_hi.json, etc.

#### Sample Usage

```
KASClient.App.getLocalizedStringsAsync(function (strings, error) {
    if (error != null) {
        return;
    }
    //use the localized strings array
});
```


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {JSON} strings can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="getlocationaddressasync"></a>

###  getLocationAddressAsync

▸ **getLocationAddressAsync**(params: *[KASLocationAddressParams](../classes/kasclient.kaslocationaddressparams.md)*, callback: *`function`*): `void`


Get address string for specified coordinates

#### Sample Usage

```
var params = new KASClient.KASLocationAddressParams();
params.latitude =  <latitude value>;
params.longitude =  <longitude value>;
KASClient.App.getLocationAddressAsync(params,
    function (address, error) {
        if (!error) {
           // do something with address - a JSON returned by google structure can be found at https://developers.google.com/maps/documentation/geocoding/intro#GeocodingResponses
        }
    }
});
```


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| params | [KASLocationAddressParams](../classes/kasclient.kaslocationaddressparams.md) |  KASLocationAddressParams |
| callback | `function` |  callback on address fetch with below params<br><br>\* @param {JSON} location a json containing latitute longitude and other informaion<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="getmapimageasbase64async"></a>

###  getMapImageAsBase64Async

▸ **getMapImageAsBase64Async**(params: *[KASLocationStaticMapImageParams](../classes/kasclient.kaslocationstaticmapimageparams.md)*, callback: *`function`*): `void`


Download the base 64 image of map for the coordinates specified

#### Sample Usage

```
KASClient.App.getMapImageAsBase64Async(params, function (attachmentString, error) {
        if (!error) {
            blobString = "data:image/jpeg;base64," + attachmentString;
            //use blobString as base64 data
        }
 });
```


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| params | [KASLocationStaticMapImageParams](../classes/kasclient.kaslocationstaticmapimageparams.md) |  KASLocationStaticMapImageParams |
| callback | `function` |  on download completion with below params<br><br>\* @param {string} attachmentString base64 value of the attachment<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="geto365userdetailsasync"></a>

###  getO365UserDetailsAsync

▸ **getO365UserDetailsAsync**(callback: *`function`*): `void`


Gets details of current logged-in O365 user


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {Json} returns the UserDetails in Json structure |

**Returns:** `void`

___




<a id="getpackagecustomsettingsasync"></a>

###  getPackageCustomSettingsAsync

▸ **getPackageCustomSettingsAsync**(callback: *`function`*): `void`


Gets all the customization settings for a package (Used in case of Type-4 packages and their base).

#### Sample Usage

```
KASClient.App.getPackageCustomSettingsAsync(function (settings, error) {
      if (error != null) {
          return;
      }
     //settings contains the settings json defined at the package level
});
```


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {JSON} settings can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="getusersdetailsasync"></a>

###  getUsersDetailsAsync

▸ **getUsersDetailsAsync**(userIds: *`string`[]*, callback: *`function`*): `void`


Gets users' details (name, pic, phone number, etc.) against their ids

#### Sample Usage

```
var userIds = ["<uid1>", "<uid2>",...];
KASClient.App.getUsersDetailsAsync(userIds, function (users, error) {
      if (error != null) {
          return;
      }
      var userInfo1 = users[<uid1>];
      var userInfo2 = users[<uid2>];
      ...
  });
```


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| userIds | `string`[] |  array of user ids |
| callback | `function` |  with below parameters:<br><br>\* @param {Dictionary<UserId: string, UserInfo: KASUser>} userIdToInfoMap (users' details against their ids) can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="hideprogressbar"></a>

###  hideProgressBar

▸ **hideProgressBar**(): `void`


Hides the current progress bar, if any


**Returns:** `void`

___




<a id="isattachmentdownloadingasync"></a>

###  isAttachmentDownloadingAsync

▸ **isAttachmentDownloadingAsync**(attachment: *[KASAttachment](../classes/kasclient.kasattachment.md)*, callback: *`function`*): `void`


Download the attachment specified

#### Sample Usage

```
var attachmentJson = {
  ty: 3,
  afn: "131490_Desert (1) (4).pdf",
  lpu: "",
  spu: '<server path>',
  asb: 846941,
  id:''
};
var attachment = KASClient.KASAttachment.fromJSON(attachmentJson);
KASClient.App.isAttachmentDownloadingAsync(attachment, function(isAttachmentDownloadingOrDownLoaded, error){
     if (!error) {
        console.log(isAttachmentDownloadingOrDownLoaded); //boolean
     }
});
```


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| attachment | [KASAttachment](../classes/kasclient.kasattachment.md) |  attachment with a valid server path to download |
| callback | `function` |  callback on download completion with below params<br><br>\* @param {boolean} isAttachmentDownloadingOrDownLoaded flag representing if attachment is downloading/downloaded<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="isauthenticationtyepsupportedasync"></a>

###  isAuthenticationTyepSupportedAsync

▸ **isAuthenticationTyepSupportedAsync**(authenticationType?: *[KASAuthenticationType](../enums/kasclient.kasauthenticationtype.md)*, callback: *`function`*): `void`


Checks if authentication of type is possible or not.


**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| `Default value` authenticationType | [KASAuthenticationType](../enums/kasclient.kasauthenticationtype.md) |  KASAuthenticationType.None |  type of authentication. |
| callback | `function` | - |  with below parameters:<br><br>\* @param {boolean} isSuccessful true if finger printing is possible<br><br>\* @param {string} reasonCode reason code why finger print is not possible |

**Returns:** `void`

___




<a id="istalkbackenabledasync"></a>

###  isTalkBackEnabledAsync

▸ **isTalkBackEnabledAsync**(callback: *`function`*): `void`


Gets whether talkback is enabled or not


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {boolean} talkBackEnabled true if talkback is enabled |

**Returns:** `void`

___




<a id="logtoreport"></a>

###  logToReport

▸ **logToReport**(data: *`string`*): `void`


Logs data for "Send report"


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| data | `string` |  string |

**Returns:** `void`

___




<a id="openattachmentimmersiveview"></a>

###  openAttachmentImmersiveView

▸ **openAttachmentImmersiveView**(attachmentObj: *[KASAttachment](../classes/kasclient.kasattachment.md)*): `void`


Open attachment in Immersive view.


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| attachmentObj | [KASAttachment](../classes/kasclient.kasattachment.md) |   |

**Returns:** `void`

___




<a id="openimmersiveviewforattachmentlist"></a>

###  openImmersiveViewForAttachmentList

▸ **openImmersiveViewForAttachmentList**(attachmentList: *[KASAttachment](../classes/kasclient.kasattachment.md)[]*, atIndex?: *`number`*): `void`


Open attachment in Immersive view.


**Parameters:**

| Name | Type | Default value |
| ------ | ------ | ------ |
| attachmentList | [KASAttachment](../classes/kasclient.kasattachment.md)[] | - |
| `Default value` atIndex | `number` | 0 |

**Returns:** `void`

___




<a id="performauthenticationasync"></a>

###  performAuthenticationAsync

▸ **performAuthenticationAsync**(authenticationType?: *[KASAuthenticationType](../enums/kasclient.kasauthenticationtype.md)*, callback: *`function`*): `void`


If authentication type is allowed, this API performs the authentication and returns success/false status else it returns an error string with reason why authentication is not possible.

#### Sample Usage

```
KASClient.App.performAuthenticationAsync(KASAuthenticationType.Password, function (isSuccessful, reasonCode) {
      if (!isSuccessful) {
          console.log(resonCode);
      }
});
```


**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| `Default value` authenticationType | [KASAuthenticationType](../enums/kasclient.kasauthenticationtype.md) |  KASAuthenticationType.None |  type of authentication. |
| callback | `function` | - |  with below parameters:<br><br>\* @param {boolean} isSuccessful true if the form is not yet expired<br><br>\* @param {string} reasonCode reason code in case of error, null otherwise |

**Returns:** `void`

___




<a id="performhttprequest"></a>

###  performHTTPRequest

▸ **performHTTPRequest**(url: *`string`*, parametersJSON: *`string`*, callback: *`function`*): `void`


performs an http request and returns the response as specified below:

#### Sample Usage

```
var url = "<url>";
var parametersJson = JSON.stringify({ "method" : "GET" });
KASClient.App.performHTTPRequest(url, parametersJson, function (response, error) {
      if (!error) {
          //use the response
      }
});
```


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| url | `string` |  base url to open |
| parametersJSON | `string` |  jsonstring containing parameters can be given as null.<br><br> If given as null a request to the url provided above will be made. Parameters include request header,query parameters(default blank), request method(default GET) and request body(The body to be posted if request method is POST. default blank.) The keys for parameters are:<br><br> a.) "method" : request method. example: "POST". defaults to "GET".<br><br> b.) "requestBody": body of request in case of "POST". defaults to blank.<br><br> c.) "requestHeaders": headers to be sent with request. should be a json with<br> key as request header and value as the desired value. defaults to blank.<br><br> d.) "queryParameters": query parameters. will be encoded in url. should be a json with<br> key as parameter name and value as its value. defaults to blank.<br><br> e.) "requestResourcePath": will be appended to base url. default is blank. |
| callback | `function` |  callback with below parameters:<br><br>\* @param {string} response response body returned<br><br> This could have two possible config:<br><br> If request was a success it returns jsonstring with following keys:<br><br> a.) "HttpResponseCode" : The response code of request.<br><br> b.) "HttpResponseHeader": The response HTTP headers<br><br> c.) "HttpResponseBody": The response body returned for request.<br><br> If there was a Network error then it returns:<br><br> a.) "HttpErrorCode": The error code<br><br> b.) "HttpErrorMessage": The error message eg. Malformed URL, Cannot connect to host etc.<br><br>\* @param {string} error error if any : This includes the standard error code defined in KASClient documentation. |

**Returns:** `void`

___




<a id="printf"></a>

###  printf

▸ **printf**(main: *`string`*, ...args: *`any`[]*): `string`


Returns a string.


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| main | `string` |
| `Rest` args | `any`[] |  array of arguments. |

**Returns:** `string`

___




<a id="readtalkbackmessage"></a>

###  readTalkBackMessage

▸ **readTalkBackMessage**(talkBackMessage: *`string`*): `void`


Reads the text if TalkBack/VoiceOver enabled


**Parameters:**

| Name | Type |
| ------ | ------ |
| talkBackMessage | `string` |

**Returns:** `void`

___




<a id="registerhardwarebackpresscallback"></a>

###  registerHardwareBackPressCallback

▸ **registerHardwareBackPressCallback**(callback?: *`function`*): `void`


Registers a callback to be executed on hardware back button press (for Android)


**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| `Default value` callback | `function` |  null |  method to be executed |

**Returns:** `void`

___




<a id="setnativetoolbarproperties"></a>

###  setNativeToolbarProperties

▸ **setNativeToolbarProperties**(properties: *[KASNativeToolbarProperties](../classes/kasclient.kasnativetoolbarproperties.md)*): `void`


Sets few properties when using native toolbar

#### Sample Usage

```
var nativeToolbarProps = new KASClient.KASNativeToolbarProperties();
nativeToolbarProps.icon = "<image>"
nativeToolbarProps.title = "<title>";
nativeToolbarProps.subtitle = "<subtitle>";
KASClient.App.setNativeToolbarProperties(nativeToolbarProps);
```


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| properties | [KASNativeToolbarProperties](../classes/kasclient.kasnativetoolbarproperties.md) |   |

**Returns:** `void`

___




<a id="setuserstrings"></a>

###  setUserStrings

▸ **setUserStrings**(strings?: *`JSON`*): `void`

**Parameters:**

| Name | Type | Default value |
| ------ | ------ | ------ |
| `Default value` strings | `JSON` |  null |

**Returns:** `void`

___




<a id="showattachmentpickerasync"></a>

###  showAttachmentPickerAsync

▸ **showAttachmentPickerAsync**(supportedTypes: *[KASAttachmentType](../enums/kasclient.kasattachmenttype.md)[]*, props: *`JSON`*, callback: *`function`*): `void`


Displays an attachment picker in the native layer

#### Sample Usage

```
var attachmentsTypesToShow = [];
attachmentsTypesToShow.push(KASClient.KASAttachmentType.Image);
attachmentsTypesToShow.push(KASClient.KASAttachmentType.Document);
attachmentsTypesToShow.push(KASClient.KASAttachmentType.Audio);
KASClient.App.showAttachmentPickerAsync(attachmentsTypesToShow, null, function (selectedAttachments, error) {
      if (error != null) {
                      return;
      }
      if (selectedAttachments && selectedAttachments.length > 0) {
          for (var i = 0; i < selectedAttachments.length; i++) {
              if (selectedAttachments[i].type == KASClient.KASAttachmentType.Image) {
                    this.imageAttachmentList.push(selectedAttachments[i]);
              }
              ...
           }...
      }
});
```


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| supportedTypes | [KASAttachmentType](../enums/kasclient.kasattachmenttype.md)[] |  array of supported attachment types for the picker. |
| props | `JSON` |  additional props to configure the picker |
| callback | `function` |  with below parameters<br><br>\* @param {KASAttachment\[\]} selectedAttachments string of selected attachments<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="showbarcodescannerasync"></a>

###  showBarcodeScannerAsync

▸ **showBarcodeScannerAsync**(callback: *`function`*): `void`


Launches the barcode scanner and returns the scanned object


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {string} barcodeInfo can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="showcontactpickerasync"></a>

###  showContactPickerAsync

▸ **showContactPickerAsync**(title: *`string`*, selectedMutableUser: *`string`[]*, selectedImmutableUser: *`string`[]*, isSingleSelection: *`boolean`*, callback: *`function`*): `void`


Shows a native contact picker, and returns an array of all the selected users' details


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| title | `string` |  of Contact Picker |
| selectedMutableUser | `string`[] |  array of selected userIds |
| selectedImmutableUser | `string`[] |  array of fixed selected userIds |
| isSingleSelection | `boolean` |  single selection in Contact Picker |
| callback | `function` |  with below parameters:<br><br>\* @param {KASUser\[\]} selectedUsers (array of user details) can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`
Array of all the selected users' details (Array of JSON)
#### Sample Usage
```
var alreadySelectedUserIds = [];
KASClient.App.showContactPickerAsync("<picker title>", alreadySelectedUserIds, [], true, function (selectedUsers, error) {
    if (error == null && selectedUsers != null && selectedUsers.length > 0) {
        var selectedUser = selectedUsers[0]; //KASUser
        console.log(selectedUser.id);
    }
});
```

___




<a id="showdurationpickerasync"></a>

###  showDurationPickerAsync

▸ **showDurationPickerAsync**(defaultDurationInMinutes: *`number`*, callback: *`function`*): `void`


Shows a native duration picker with day/hour/minute


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| defaultDurationInMinutes | `number` |  the default duration to be shown on picker |
| callback | `function` |  with below parameters:<br><br>\* @param {number} durationInMinutes selected duration in minutes<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="showimageimmersiveview"></a>

###  showImageImmersiveView

▸ **showImageImmersiveView**(urls?: *`string`[]*, currentImageIndex?: *`number`*): `void`


Shows Image in Immersive view.

#### Sample Usage

```
var urlArray = ["path1", "path2"];
KASClient.App.showImageImmersiveView(urlArray);
```


**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| `Default value` urls | `string`[] |  [] |  Array of images url: |
| `Default value` currentImageIndex | `number` | 0 |

**Returns:** `void`

___




<a id="showimagepickerasync"></a>

###  showImagePickerAsync

▸ **showImagePickerAsync**(callback: *`function`*): `void`


Shows a native image picker, and returns the selected image path


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {string} selectedImagePath can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`
Selected image location

___




<a id="showlocationonmap"></a>

###  showLocationOnMap

▸ **showLocationOnMap**(location: *[KASLocation](../classes/kasclient.kaslocation.md)*): `void`


shows a particular location as mentioned in KASLocation


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| location | [KASLocation](../classes/kasclient.kaslocation.md) |   |

**Returns:** `void`

___




<a id="shownativeerrormessage"></a>

###  showNativeErrorMessage

▸ **showNativeErrorMessage**(message: *`string`*): `void`


Shows a native alert (for iOS) or a toast (for Android) with the message


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| message | `string` |   |

**Returns:** `void`

___




<a id="showplacepickerasync"></a>

###  showPlacePickerAsync

▸ **showPlacePickerAsync**(callback: *`function`*): `void`


Shows a native place picker, and returns the selected place (lt, lg, n)


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {KASLocation} selectedLocation can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="showprogressbar"></a>

###  showProgressBar

▸ **showProgressBar**(text: *`string`*): `void`


Shows a native full sreen progress bar with the given text


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| text | `string` |   |

**Returns:** `void`

___




<a id="showqrcodescannerasync"></a>

###  showQRcodeScannerAsync

▸ **showQRcodeScannerAsync**(callback: *`function`*): `void`


Launches the QR code scanner and returns the scanned object


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {string} qrCodeInfo can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="showuserprofileasync"></a>

###  showUserProfileAsync

▸ **showUserProfileAsync**(userId: *`string`*, isMiniProfile: *`boolean`*, callback: *`function`*): `void`


Shows profile page/details of a user


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| userId | `string` |  of the user whose profile is to be shown |
| isMiniProfile | `boolean` |  whether to show mini-profile first |
| callback | `function` |  with below parameters:<br><br>\* @param {boolean} success true if successful, false otherwise<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___




<a id="startchatasync"></a>

###  startChatAsync

▸ **startChatAsync**(userId: *`string`*, callback: *`function`*): `void`


Starts chat with a user


**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| userId | `string` |  of the user |
| callback | `function` |  with below parameters:<br><br>\* @param {boolean} success<br><br>\* @param {string} error |

**Returns:** `void`

___





