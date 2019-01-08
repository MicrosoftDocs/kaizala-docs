[type-doc](../README.md) > [KASClient](../modules/kasclient.md) > [App](../modules/kasclient.app.md)

# Module: App

## Index

### Variables

* [hardwareBackPressCallback](kasclient.app.md#hardwarebackpresscallback)

### Functions

* [OnHardwareBackPress](kasclient.app.md#onhardwarebackpress)
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
* [launchShare](kasclient.app.md#launchshare)
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
* [showLocationOnMap](kasclient.app.md#showlocationonmap)
* [showNativeErrorMessage](kasclient.app.md#shownativeerrormessage)
* [showPlacePickerAsync](kasclient.app.md#showplacepickerasync)
* [showProgressBar](kasclient.app.md#showprogressbar)
* [showQRcodeScannerAsync](kasclient.app.md#showqrcodescannerasync)
* [showUserProfileAsync](kasclient.app.md#showuserprofileasync)
* [startChatAsync](kasclient.app.md#startchatasync)

---

## Variables

<a id="hardwarebackpresscallback"></a>

###  hardwareBackPressCallback

**● hardwareBackPressCallback**: *`function`* =  null

*Defined in AppAPIs.ts:993*

Registers a callback to be executed on hardware back button press (for Android)
*__param__*: to be executed

#### Type declaration
▸(): `void`

**Returns:** `void`

___

## Functions

<a id="onhardwarebackpress"></a>

###  OnHardwareBackPress

▸ **OnHardwareBackPress**(): `void`

*Defined in AppAPIs.ts:999*

**Returns:** `void`

___
<a id="cancelattachmentdownloadasync"></a>

###  cancelAttachmentDownloadAsync

▸ **cancelAttachmentDownloadAsync**(attachment: *[KASAttachment](../classes/kasclient.kasattachment.md)*, callback: *`function`*): `void`

*Defined in AppAPIs.ts:377*

*__example__*: ```typescript

 var attachmentsList = JSON.parse(form.properties[0].value);
 for (var i = 0; i < attachmentsList.length; i++)
 {
      var attachmentItem = attachmentsList[i];
      var attachment = KASClient.KASAttachment.fromJSON(attachmentItem);
      KASClient.App.cancelAttachmentDownloadAsync(attachment);
 }
```

Cancel a download operation queued for an attachment

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| attachment | [KASAttachment](../classes/kasclient.kasattachment.md) |   |
| callback | `function` |

**Returns:** `void`

___
<a id="dismisscurrentscreen"></a>

###  dismissCurrentScreen

▸ **dismissCurrentScreen**(): `void`

*Defined in AppAPIs.ts:670*

Dismiss the current screen (Creation, Response, or Summary)

**Returns:** `void`

___
<a id="downloadattachmentasync"></a>

###  downloadAttachmentAsync

▸ **downloadAttachmentAsync**(attachment: *[KASAttachment](../classes/kasclient.kasattachment.md)*, callback: *`function`*): `void`

*Defined in AppAPIs.ts:321*

*__example__*: ```typescript

var attachmentJson = {
  ty: 3,
  afn: "131490_Desert (1) (4).pdf",
  lpu: "",
  spu: '<server path>',
  asb: 846941,
  id:''
};
var attachment = KASClient.KASAttachment.fromJSON(attachmentJson);
KASClient.App.downloadAttachmentAsync(attachment, function(downloadedAttachment, error){
     if (!error) {
        console.log(downloadedAttachment); //KASAttachment
     }
});
```

Download the attachment specified

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| attachment | [KASAttachment](../classes/kasclient.kasattachment.md) |  attachment with a valid server path to download |
| callback | `function` |  callback on download completion |

**Returns:** `void`

___
<a id="generatebase64thumbnailasync"></a>

###  generateBase64ThumbnailAsync

▸ **generateBase64ThumbnailAsync**(localPath: *`string`*, callback: *`function`*): `void`

*Defined in AppAPIs.ts:838*

*__example__*: ```typescript

KASClient.App.generateBase64ThumbnailAsync(localPath, function (thumbnail, error) {
    if (error == null && thumbnail != null) {
       //use the thumbnail data and update required dom
     }
});
```

Generates Base64 thumbnail for an image whose localPath is given

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| localPath | `string` |  localPath for the imageAttachment whose thumbnail needs to be generated: |
| callback | `function` |

**Returns:** `void`

___
<a id="generateuuidasync"></a>

###  generateUUIDAsync

▸ **generateUUIDAsync**(callback: *`function`*): `void`

*Defined in AppAPIs.ts:478*

*__example__*: ```typescript

 KASClient.App.generateUUIDAsync(function (uuid, error) {
    console.log("generatedUUIDAsync", uuid);
    ...
 });
```

Gets the new UUID

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {string} uuid newly generated uuid*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="getapplocaleasync"></a>

###  getAppLocaleAsync

▸ **getAppLocaleAsync**(callback: *`function`*): `void`

*Defined in AppAPIs.ts:541*

Gets the current app locale, the language in which the app is rendered, useful for localizing MiniApp's strings

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {string} locale can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="getcalendarnameasync"></a>

###  getCalendarNameAsync

▸ **getCalendarNameAsync**(callback: *`function`*): `void`

*Defined in AppAPIs.ts:579*

Gets the current system calendar setting. This is mainly for iOS to identify the calendar name set in phone setting like Gregorian or Japanese or Buddhists.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {string} calendarName can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="getconversationdetailsasync"></a>

###  getConversationDetailsAsync

▸ **getConversationDetailsAsync**(callback: *`function`*): `void`

*Defined in AppAPIs.ts:1226*

Gets conversation related properties

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   *   *   @param {KASConversationDetails} result conversation properties*   *   *   @param {string} error json string for the KASError object containing error code and/or description. |

**Returns:** `void`

___
<a id="getcurrentdevicelocationasync"></a>

###  getCurrentDeviceLocationAsync

▸ **getCurrentDeviceLocationAsync**(callback: *`function`*): `void`

*Defined in AppAPIs.ts:505*

*__example__*: ```typescript

 KASClient.App.getCurrentDeviceLocationAsync(function (location, error){
     if(error != null) {
          return;
     }
     //use location(KASLocation) as the device location
 });
```

Gets the current device location

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {string} location can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="getcurrentlocale"></a>

###  getCurrentLocale

▸ **getCurrentLocale**(): `string`

*Defined in AppAPIs.ts:1097*

**Returns:** `string`

___
<a id="getdeviceidasync"></a>

###  getDeviceIdAsync

▸ **getDeviceIdAsync**(callback: *`function`*): `void`

*Defined in AppAPIs.ts:115*

Gets deviceId

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {string} deviceId got from integeration service*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="getdevicelocationasync"></a>

###  getDeviceLocationAsync

▸ **getDeviceLocationAsync**(callback: *`function`*): `void`

*Defined in AppAPIs.ts:448*

Gets the previously stored device location

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {string} location can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="getfontsizemultiplierasync"></a>

###  getFontSizeMultiplierAsync

▸ **getFontSizeMultiplierAsync**(callback: *`function`*): `void`

*Defined in AppAPIs.ts:850*

Gets the font size multiplier for large text. Current only required by iOS.

**Parameters:**

| Name | Type |
| ------ | ------ |
| callback | `function` |

**Returns:** `void`

___
<a id="getforwardcontextasync"></a>

###  getForwardContextAsync

▸ **getForwardContextAsync**(callback: *`function`*): `void`

*Defined in AppAPIs.ts:968*

Gets Forward Context details such as : Card Creation is in forwarded mode

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {Json} returns the Context Details in Json structure |

**Returns:** `void`

___
<a id="getisapptimeformat24hoursasync"></a>

###  getIsAppTimeFormat24HoursAsync

▸ **getIsAppTimeFormat24HoursAsync**(callback: *`function`*): `void`

*Defined in AppAPIs.ts:560*

Gets the current app time format is 24hours or not, the time format selected by user, useful for formatting date time strings properly

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {string} isAppTimeFormat24Hours can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="getlocalizedstringsasync"></a>

###  getLocalizedStringsAsync

▸ **getLocalizedStringsAsync**(callback: *`function`*): `void`

*Defined in AppAPIs.ts:871*

*__example__*: ```typescript

KASClient.App.getLocalizedStringsAsync(function (strings, error) {
    if (error != null) {
        return;
    }
    //use the localized strings array
});
```

Gets the localized strings' dictionary based on current app locale. Strings must be provided inside the package with names like: strings\_en.json, strings\_hi.json, etc.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {JSON} strings can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="getlocationaddressasync"></a>

###  getLocationAddressAsync

▸ **getLocationAddressAsync**(params: *[KASLocationAddressParams](../classes/kasclient.kaslocationaddressparams.md)*, callback: *`function`*): `void`

*Defined in AppAPIs.ts:290*

*__example__*: ```typescript

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

Get address string for specified coordinates

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| params | [KASLocationAddressParams](../classes/kasclient.kaslocationaddressparams.md) |  KASLocationAddressParams |
| callback | `function` |  callback on address fetch |

**Returns:** `void`

___
<a id="getmapimageasbase64async"></a>

###  getMapImageAsBase64Async

▸ **getMapImageAsBase64Async**(params: *[KASLocationStaticMapImageParams](../classes/kasclient.kaslocationstaticmapimageparams.md)*, callback: *`function`*): `void`

*Defined in AppAPIs.ts:263*

*__example__*: ```typescript

KASClient.App.getMapImageAsBase64Async(params, function (attachmentString, error) {
        if (!error) {
            blobString = "data:image/jpeg;base64," + attachmentString;
            //use blobString as base64 data
        }
 });
```

Download the base 64 image of map for the coordinates specified

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| params | [KASLocationStaticMapImageParams](../classes/kasclient.kaslocationstaticmapimageparams.md) |  KASLocationStaticMapImageParams |
| callback | `function` |  callback on download completion |

**Returns:** `void`

___
<a id="geto365userdetailsasync"></a>

###  getO365UserDetailsAsync

▸ **getO365UserDetailsAsync**(callback: *`function`*): `void`

*Defined in AppAPIs.ts:952*

Gets details of current logged-in O365 user

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {Json} returns the UserDetails in Json structure |

**Returns:** `void`

___
<a id="getpackagecustomsettingsasync"></a>

###  getPackageCustomSettingsAsync

▸ **getPackageCustomSettingsAsync**(callback: *`function`*): `void`

*Defined in AppAPIs.ts:891*

*__example__*: ```typescript

KASClient.App.getPackageCustomSettingsAsync(function (settings, error) {
      if (error != null) {
          return;
      }
     //settings contains the settings json defined at the package level
});
```

Gets all the customization settings for a package (Used in case of Type-4 packages and their base).

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {JSON} settings can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="getusersdetailsasync"></a>

###  getUsersDetailsAsync

▸ **getUsersDetailsAsync**(userIds: *`string`[]*, callback: *`function`*): `void`

*Defined in AppAPIs.ts:34*

*__example__*: ```typescript

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

Gets users' details (name, pic, phone number, etc.) against their ids

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| userIds | `string`[] |  array of user ids |
| callback | `function` |  with below parameters:*   @param {Dictionary<UserId: string, UserInfo: KASUser>} userIdToInfoMap (users' details against their ids) can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="hideprogressbar"></a>

###  hideProgressBar

▸ **hideProgressBar**(): `void`

*Defined in AppAPIs.ts:692*

Hides the current progress bar, if any

**Returns:** `void`

___
<a id="isattachmentdownloadingasync"></a>

###  isAttachmentDownloadingAsync

▸ **isAttachmentDownloadingAsync**(attachment: *[KASAttachment](../classes/kasclient.kasattachment.md)*, callback: *`function`*): `void`

*Defined in AppAPIs.ts:353*

*__example__*: ```typescript

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

Download the attachment specified

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| attachment | [KASAttachment](../classes/kasclient.kasattachment.md) |  attachment with a valid server path to download |
| callback | `function` |  callback on download completion |

**Returns:** `void`

___
<a id="isauthenticationtyepsupportedasync"></a>

###  isAuthenticationTyepSupportedAsync

▸ **isAuthenticationTyepSupportedAsync**(authenticationType?: *[KASAuthenticationType](../enums/kasclient.kasauthenticationtype.md)*, callback: *`function`*): `void`

*Defined in AppAPIs.ts:1136*

Checks if authentication of type is possible or not.

**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| `Default value` authenticationType | [KASAuthenticationType](../enums/kasclient.kasauthenticationtype.md) |  KASAuthenticationType.None |  type of authentication. |
| callback | `function` | - |  with below parameters:*   @param {boolean} isSuccessful true if finger printing is possible*   @param {string} reasonCode reason code why finger print is not possible |

**Returns:** `void`

___
<a id="istalkbackenabledasync"></a>

###  isTalkBackEnabledAsync

▸ **isTalkBackEnabledAsync**(callback: *`function`*): `void`

*Defined in AppAPIs.ts:173*

Gets whether talkback is enabled or not

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {boolean} talkBackEnabled true if talkback is enabled |

**Returns:** `void`

___
<a id="launchshare"></a>

###  launchShare

▸ **launchShare**(objects: *[KASShareObject](../classes/kasclient.kasshareobject.md)[]*, callback: *`function`*): `void`

*Defined in AppAPIs.ts:1235*

**Parameters:**

| Name | Type |
| ------ | ------ |
| objects | [KASShareObject](../classes/kasclient.kasshareobject.md)[] |
| callback | `function` |

**Returns:** `void`

___
<a id="logtoreport"></a>

###  logToReport

▸ **logToReport**(data: *`string`*): `void`

*Defined in AppAPIs.ts:908*

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

*Defined in AppAPIs.ts:781*

*__example__*: ```typescript

Attachment should be available locally - so download it before opening - if already downloaded simply call the API
var attachmentJson = {
  ty: 3,
  afn: "131490_Desert (1) (4).pdf",
  lpu: "",
  spu: '<server path>',
  asb: 846941,
  id:''
};
var attachment = KASClient.KASAttachment.fromJSON(attachmentJson);
KASClient.App.downloadAttachmentAsync(attachment, function(downloadedAttachment, error){
     if (!error) {
        KASClient.App.openAttachmentImmersiveView(downloadedAttachment);
     }
});
```

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

*Defined in AppAPIs.ts:808*

*   @example `` ` ``typescript

Attachment should be available locally - so download it before opening - if already downloaded simply call the API var attachmentJson = { ty: 3, afn: "131490\_Desert (1) (4).pdf", lpu: "", spu: '', asb: 846941, id:'' }; var attachment = KASClient.KASAttachment.fromJSON(attachmentJson); KASClient.App.downloadAttachmentAsync(attachment, function(downloadedAttachment, error){ if (!error) { KASClient.App.openImmersiveViewForAttachmentList(\[downloadedAttachment\], 0); } }); `` ` `` Open attachment in Immersive view.

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

*Defined in AppAPIs.ts:1119*

*__example__*: ```typescript

KASClient.App.performAuthenticationAsync(KASAuthenticationType.Password, function (isSuccessful, reasonCode) {
      if (!isSuccessful) {
          console.log(resonCode);
      }
});
```

If authentication type is allowed, this API performs the authentication and returns success/false status else it returns an error string with reason why authentication is not possible.

**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| `Default value` authenticationType | [KASAuthenticationType](../enums/kasclient.kasauthenticationtype.md) |  KASAuthenticationType.None |  type of authentication. |
| callback | `function` | - |  with below parameters:*   @param {boolean} isSuccessful true if the form is not yet expired*   @param {string} reasonCode reason code in case of error, null otherwise |

**Returns:** `void`

___
<a id="performhttprequest"></a>

###  performHTTPRequest

▸ **performHTTPRequest**(url: *`string`*, parametersJSON: *`string`*, callback: *`function`*): `void`

*Defined in AppAPIs.ts:1209*

*__example__*: ```typescript

var url = "<url>";
var parametersJson = JSON.stringify({ "method" : "GET" });
KASClient.App.performHTTPRequest(url, parametersJson, function (response, error) {
      if (!error) {
          //use the response
      }
});
```

performs an http request and returns the response as specified below:

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| url | `string` |  base url to open |
| parametersJSON | `string` |  jsonstring containing parameters can be given as null. If given as null a request to the url provided above will be made. Parameters include request header,query parameters(default blank), request method(default GET) and request body(The body to be posted if request method is POST. default blank.) The keys for parameters are: a.) "method" : request method. example: "POST". defaults to "GET". b.) "requestBody": body of request in case of "POST". defaults to blank. c.) "requestHeaders": headers to be sent with request. should be a json with key as request header and value as the desired value. defaults to blank. d.) "queryParameters": query parameters. will be encoded in url. should be a json with key as parameter name and value as its value. defaults to blank. e.) "requestResourcePath": will be appended to base url. default is blank. |
| callback | `function` |  callback with below parameters:*   @param {string} response response body returned```This could have two possible config:If request was a success it returns jsonstring with following keys:a.) &quot;HttpResponseCode&quot; : The response code of request.b.) &quot;HttpResponseHeader&quot;: The response HTTP headersc.) &quot;HttpResponseBody&quot;: The response body returned for request.If there was a Network error then it returns:a.) &quot;HttpErrorCode&quot;: The error codeb.) &quot;HttpErrorMessage&quot;: The error message eg. Malformed URL, Cannot connect to host etc.```*   @param {string} error error if any : This includes the standard error code defined in KASClient documentation. |

**Returns:** `void`

___
<a id="printf"></a>

###  printf

▸ **printf**(main: *`string`*, ...args: *`any`[]*): `string`

*Defined in AppAPIs.ts:1087*

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

*Defined in AppAPIs.ts:185*

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

*Defined in AppAPIs.ts:994*

**Parameters:**

| Name | Type | Default value |
| ------ | ------ | ------ |
| `Default value` callback | `function` |  null |

**Returns:** `void`

___
<a id="setnativetoolbarproperties"></a>

###  setNativeToolbarProperties

▸ **setNativeToolbarProperties**(properties: *[KASNativeToolbarProperties](../classes/kasclient.kasnativetoolbarproperties.md)*): `void`

*Defined in AppAPIs.ts:729*

*__example__*: ```typescript

var nativeToolbarProps = new KASClient.UI.KASNativeToolbarProperties();
nativeToolbarProps.icon = "<image>"
nativeToolbarProps.title = "<title>";
nativeToolbarProps.subtitle = "<subtitle>";
KASClient.App.setNativeToolbarProperties(nativeToolbarProps);
```

Sets few properties when using native toolbar

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| properties | [KASNativeToolbarProperties](../classes/kasclient.kasnativetoolbarproperties.md) |   |

**Returns:** `void`

___
<a id="setuserstrings"></a>

###  setUserStrings

▸ **setUserStrings**(strings?: *`JSON`*): `void`

*Defined in AppAPIs.ts:1042*

**Parameters:**

| Name | Type | Default value |
| ------ | ------ | ------ |
| `Default value` strings | `JSON` |  null |

**Returns:** `void`

___
<a id="showattachmentpickerasync"></a>

###  showAttachmentPickerAsync

▸ **showAttachmentPickerAsync**(supportedTypes: *[KASAttachmentType](../enums/kasclient.kasattachmenttype.md)[]*, props: *`JSON`*, callback: *`function`*): `void`

*Defined in AppAPIs.ts:236*

Displays an attachment picker in the native layer
*__example__*: ```typescript

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
| callback | `function` |  callback with list of selected attachments |

**Returns:** `void`

___
<a id="showbarcodescannerasync"></a>

###  showBarcodeScannerAsync

▸ **showBarcodeScannerAsync**(callback: *`function`*): `void`

*Defined in AppAPIs.ts:405*

Launches the barcode scanner and returns the scanned object

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {string} barcodeInfo can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="showcontactpickerasync"></a>

###  showContactPickerAsync

▸ **showContactPickerAsync**(title: *`string`*, selectedMutableUser: *`string`[]*, selectedImmutableUser: *`string`[]*, isSingleSelection: *`boolean`*, callback: *`function`*): `void`

*Defined in AppAPIs.ts:144*

*__example__*: ```typescript

var alreadySelectedUserIds = [];
KASClient.App.showContactPickerAsync("<picker title>", alreadySelectedUserIds, [], true, function (selectedUsers, error) {
    if (error == null && selectedUsers != null && selectedUsers.length > 0) {
        var selectedUser = selectedUsers[0]; //KASUser
        console.log(selectedUser.id);
    }
});
```

Shows a native contact picker, and returns an array of all the selected users' details

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| title | `string` |  of Contact Picker |
| selectedMutableUser | `string`[] |  array of selected userIds |
| selectedImmutableUser | `string`[] |  array of fixed selected userIds |
| isSingleSelection | `boolean` |  single selection in Contact Picker |
| callback | `function` |  with below parameters:*   @param {KASUser\[\]} selectedUsers (array of user details) can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="showdurationpickerasync"></a>

###  showDurationPickerAsync

▸ **showDurationPickerAsync**(defaultDurationInMinutes: *`number`*, callback: *`function`*): `void`

*Defined in AppAPIs.ts:434*

Shows a native duration picker with day/hour/minute

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| defaultDurationInMinutes | `number` |  the default duration to be shown on picker |
| callback | `function` |  with below parameters:*   @param {number} durationInMinutes selected duration in minutes*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="showimageimmersiveview"></a>

###  showImageImmersiveView

▸ **showImageImmersiveView**(urls?: *`string`[]*, currentImageIndex?: *`number`*): `void`

*Defined in AppAPIs.ts:754*

*__example__*: ```typescript

var urlArray = ["path1", "path2"];
KASClient.App.showImageImmersiveView(urlArray);
```

Shows Image in Immersive view.

**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| `Default value` urls | `string`[] |  [] |  Array of images url: |
| `Default value` currentImageIndex | `number` | 0 |

**Returns:** `void`

___
<a id="showlocationonmap"></a>

###  showLocationOnMap

▸ **showLocationOnMap**(location: *[KASLocation](../classes/kasclient.kaslocation.md)*): `void`

*Defined in AppAPIs.ts:1078*

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

*Defined in AppAPIs.ts:524*

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

*Defined in AppAPIs.ts:391*

Shows a native place picker, and returns the selected place (lt, lg, n)

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {KASLocation} selectedLocation can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="showprogressbar"></a>

###  showProgressBar

▸ **showProgressBar**(text: *`string`*): `void`

*Defined in AppAPIs.ts:685*

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

*Defined in AppAPIs.ts:419*

Launches the QR code scanner and returns the scanned object

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {string} qrCodeInfo can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="showuserprofileasync"></a>

###  showUserProfileAsync

▸ **showUserProfileAsync**(userId: *`string`*, isMiniProfile: *`boolean`*, callback: *`function`*): `void`

*Defined in AppAPIs.ts:74*

Shows profile page/details of a user

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| userId | `string` |  of the user whose profile is to be shown |
| isMiniProfile | `boolean` |  whether to show mini-profile first |
| callback | `function` |

**Returns:** `void`

___
<a id="startchatasync"></a>

###  startChatAsync

▸ **startChatAsync**(userId: *`string`*, callback: *`function`*): `void`

*Defined in AppAPIs.ts:86*

Starts chat with a user

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| userId | `string` |  of the user |
| callback | `function` |

**Returns:** `void`

___

