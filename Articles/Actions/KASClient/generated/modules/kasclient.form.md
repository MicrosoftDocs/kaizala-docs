[type-doc](../README.md) > [KASClient](../modules/kasclient.md) > [Form](../modules/kasclient.form.md)

# Module: Form

## Index

### Type aliases

* [FormSummaryCallback](kasclient.form.md#formsummarycallback)

### Functions

* [addCommentOnForm](kasclient.form.md#addcommentonform)
* [closeForm](kasclient.form.md#closeform)
* [copyFormAndForward](kasclient.form.md#copyformandforward)
* [getActionInstanceLocalDataCacheAsync](kasclient.form.md#getactioninstancelocaldatacacheasync)
* [getActionPackageLocalDataCacheAsync](kasclient.form.md#getactionpackagelocaldatacacheasync)
* [getFormAsync](kasclient.form.md#getformasync)
* [getFormReactionAsync](kasclient.form.md#getformreactionasync)
* [getFormStatusAsync](kasclient.form.md#getformstatusasync)
* [getFormSummaryAsync](kasclient.form.md#getformsummaryasync)
* [getFormURLAsync](kasclient.form.md#getformurlasync)
* [getFormUserCapabilitiesAsync](kasclient.form.md#getformusercapabilitiesasync)
* [getMyFormResponsesAsync](kasclient.form.md#getmyformresponsesasync)
* [initFormAsync](kasclient.form.md#initformasync)
* [isSubscribed](kasclient.form.md#issubscribed)
* [likeForm](kasclient.form.md#likeform)
* [sendRemindersToRespond](kasclient.form.md#sendreminderstorespond)
* [shareFormURL](kasclient.form.md#shareformurl)
* [showAllReactions](kasclient.form.md#showallreactions)
* [submitFormRequestV2](kasclient.form.md#submitformrequestv2)
* [submitFormRequestWithoutDismiss](kasclient.form.md#submitformrequestwithoutdismiss)
* [sumbitFormResponse](kasclient.form.md#sumbitformresponse)
* [sumbitFormResponseWithoutDismiss](kasclient.form.md#sumbitformresponsewithoutdismiss)
* [updateActionInstanceLocalDataCacheAsync](kasclient.form.md#updateactioninstancelocaldatacacheasync)
* [updateActionPackageLocalDataCacheAsync](kasclient.form.md#updateactionpackagelocaldatacacheasync)
* [updateForm](kasclient.form.md#updateform)
* [updateFormPropertiesAsync](kasclient.form.md#updateformpropertiesasync)

---

## Type aliases

<a id="formsummarycallback"></a>

###  FormSummaryCallback

**Ƭ FormSummaryCallback**: *`function`*

*Defined in FormAPIs.ts:364*

#### Type declaration
▸(flatSummary: *[KASFormFlatSummary](../classes/kasclient.kasformflatsummary.md)*, processedSummary: *[KASFormProcessedSummary](../classes/kasclient.kasformprocessedsummary.md)*, error: *`string`*): `void`

**Parameters:**

| Name | Type |
| ------ | ------ |
| flatSummary | [KASFormFlatSummary](../classes/kasclient.kasformflatsummary.md) |
| processedSummary | [KASFormProcessedSummary](../classes/kasclient.kasformprocessedsummary.md) |
| error | `string` |

**Returns:** `void`

___

## Functions

<a id="addcommentonform"></a>

###  addCommentOnForm

▸ **addCommentOnForm**(comment: *`string`*): `void`

*Defined in FormAPIs.ts:652*

Requests to add a comment to a form
*__category__*: summary

**Parameters:**

| Name | Type |
| ------ | ------ |
| comment | `string` |

**Returns:** `void`

___
<a id="closeform"></a>

###  closeForm

▸ **closeForm**(): `void`

*Defined in FormAPIs.ts:713*

Closes the form associated with the card, no responses will be allowed further
*__category__*: summary

**Returns:** `void`

___
<a id="copyformandforward"></a>

###  copyFormAndForward

▸ **copyFormAndForward**(): `void`

*Defined in FormAPIs.ts:698*

Launches the conversation picker to forward a copy of the existing form as a new conversation card
*__category__*: summary

**Returns:** `void`

___
<a id="getactioninstancelocaldatacacheasync"></a>

###  getActionInstanceLocalDataCacheAsync

▸ **getActionInstanceLocalDataCacheAsync**(callback: *`function`*): `void`

*Defined in FormAPIs.ts:849*

Retrieves the ActionInstance Properties from the local data cache if any exists These properties are stored at an action instance level. So the local data saved for the particular action instance will be returned by this API.
*__category__*: summary

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   *   *   @param {KASActionProperties} actionProperties ActionInstance/Form Properties*   *   *   @param {string} error json string for the KASError object containing error code and/or description. |

**Returns:** `void`

___
<a id="getactionpackagelocaldatacacheasync"></a>

###  getActionPackageLocalDataCacheAsync

▸ **getActionPackageLocalDataCacheAsync**(callback: *`function`*): `void`

*Defined in FormAPIs.ts:812*

Retrieves the Action Package Properties from the local data cache if any exists These properties are saved at the action package level. So all action instances created from this action package will receive the same data.
*__category__*: summary

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   *   *   @param {KASActionPackageProperties} actionPackageProperties Action Package Properties*   *   *   @param {string} error json string for the KASError object containing error code and/or description. |

**Returns:** `void`

___
<a id="getformasync"></a>

###  getFormAsync

▸ **getFormAsync**(callback: *`function`*): `void`

*Defined in FormAPIs.ts:141*

Gets the form object associated with the conversation card
*__category__*: response

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {KASForm} form can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="getformreactionasync"></a>

###  getFormReactionAsync

▸ **getFormReactionAsync**(callback: *`function`*): `void`

*Defined in FormAPIs.ts:599*

Gets the consolidated reaction (likes and comments) of the conversation card associated with the form
*__category__*: summary

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {KASFormReaction} reaction can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="getformstatusasync"></a>

###  getFormStatusAsync

▸ **getFormStatusAsync**(callback: *`function`*): `void`

*Defined in FormAPIs.ts:167*

Gets the status of the form associated with the conversation card
*__category__*: response

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {boolean} isActive true if the form is not yet expired*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="getformsummaryasync"></a>

###  getFormSummaryAsync

▸ **getFormSummaryAsync**(mostUpdatedCallback: *[FormSummaryCallback](kasclient.form.md#formsummarycallback)*, notifyCallback: *[FormSummaryCallback](kasclient.form.md#formsummarycallback)*): `void`

*Defined in FormAPIs.ts:385*

Gets flat responses by all the users, and processed summary from all the responses associated with the form. It requires two callbacks:
*__category__*: summary

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| mostUpdatedCallback | [FormSummaryCallback](kasclient.form.md#formsummarycallback) |  to immediately get the most updated summary from local database. It has below parameters:*   @param {KASFormFlatSummary} flatSummary can be null in case of error*   @param {KASFormProcessedSummary} processedSummary can be null in case of error*   @param {string} error message in case of error, null otherwise |
| notifyCallback | [FormSummaryCallback](kasclient.form.md#formsummarycallback) |  to get notified with the latest summary fetched from server. It has below parameters:*   @param {KASFormFlatSummary} flatSummary can be null in case of error*   @param {KASFormProcessedSummary} processedSummary can be null in case of error*   @param {string} error message in case of error, null otherwise<br><br>This is useful when the network is flaky/disconnected, so that summary can immediately be shown with the present data we have, but with an option to refresh it later on arrival of latest data from server! None of the callbacks are mandatory, so if 1st is nil, this method can be used to always fetch summary from server, and if 2nd is nil, this can be used to always fetch summary from local database! |

**Returns:** `void`

___
<a id="getformurlasync"></a>

###  getFormURLAsync

▸ **getFormURLAsync**(callback: *`function`*): `void`

*Defined in FormAPIs.ts:559*

Gets the file url from server containing flat responses associated with the form
*__category__*: summary

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {string} url can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="getformusercapabilitiesasync"></a>

###  getFormUserCapabilitiesAsync

▸ **getFormUserCapabilitiesAsync**(callback: *`function`*): `void`

*Defined in FormAPIs.ts:342*

Gets form permissions
*__category__*: summary

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {KASFormUserCapabilities} permissions |

**Returns:** `void`

___
<a id="getmyformresponsesasync"></a>

###  getMyFormResponsesAsync

▸ **getMyFormResponsesAsync**(callback: *`function`*): `void`

*Defined in FormAPIs.ts:191*

Gets all the responses of the current user against the form
*__category__*: response

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {KASFormResponse\[\]} responses can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="initformasync"></a>

###  initFormAsync

▸ **initFormAsync**(callback: *`function`*): `void`

*Defined in FormAPIs.ts:13*

Initializes and returns an empty form object based on the default form file present in the package
*__category__*: creation

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {KASForm} form can be null in case of error*   @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="issubscribed"></a>

###  isSubscribed

▸ **isSubscribed**(callback: *`function`*): `void`

*Defined in FormAPIs.ts:356*

Gets whether the current user is subscriber or not
*__category__*: summary

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:*   @param {boolean} isSubscribed true if current user subscriber |

**Returns:** `void`

___
<a id="likeform"></a>

###  likeForm

▸ **likeForm**(): `void`

*Defined in FormAPIs.ts:637*

Requests to add a like count to a form, the count may decrease if the current user has already liked the form
*__category__*: summary

**Returns:** `void`

___
<a id="sendreminderstorespond"></a>

###  sendRemindersToRespond

▸ **sendRemindersToRespond**(): `void`

*Defined in FormAPIs.ts:683*

Sends a reminder (a new conversation card) against the existing card
*__category__*: summary

**Returns:** `void`

___
<a id="shareformurl"></a>

###  shareFormURL

▸ **shareFormURL**(url: *`string`*): `void`

*Defined in FormAPIs.ts:581*

Launches native share screen for the form url
*__category__*: summary

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| url | `string` |  to be shared |

**Returns:** `void`

___
<a id="showallreactions"></a>

###  showAllReactions

▸ **showAllReactions**(showComments?: *`boolean`*): `void`

*Defined in FormAPIs.ts:622*

Shows all the reaction screen (likes and comments) against the form
*__category__*: summary

**Parameters:**

| Name | Type | Default value |
| ------ | ------ | ------ |
| `Default value` showComments | `boolean` | true |

**Returns:** `void`

___
<a id="submitformrequestv2"></a>

###  submitFormRequestV2

▸ **submitFormRequestV2**(form: *[KASForm](../classes/kasclient.kasform.md)*, shouldDismiss?: *`boolean`*, shouldSendToSubscribers?: *`boolean`*): `void`

*Defined in FormAPIs.ts:54*

Submits the newly created form as a request. This results a new conversation card
*__category__*: creation

**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| form | [KASForm](../classes/kasclient.kasform.md) | - |  \- |
| `Default value` shouldDismiss | `boolean` | false |
| `Default value` shouldSendToSubscribers | `boolean` | true |

**Returns:** `void`

___
<a id="submitformrequestwithoutdismiss"></a>

###  submitFormRequestWithoutDismiss

▸ **submitFormRequestWithoutDismiss**(form: *[KASForm](../classes/kasclient.kasform.md)*, shouldInflate: *`boolean`*): `void`

*Defined in FormAPIs.ts:88*

Submits the newly created form as a request. This results a new conversation card
*__category__*: creation

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| form | [KASForm](../classes/kasclient.kasform.md) |  \- |
| shouldInflate | `boolean` |

**Returns:** `void`

___
<a id="sumbitformresponse"></a>

###  sumbitFormResponse

▸ **sumbitFormResponse**(questionToAnswerMap: *`JSON`*, responseId: *`string`*, isEdit: *`boolean`*, showInChatCanvas: *`boolean`*, isAnonymous: *`boolean`*): `void`

*Defined in FormAPIs.ts:273*

Submits a new response against the form associated with the conversation card This will dismiss the current screen
*__category__*: response

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| questionToAnswerMap | `JSON` |  question id to answer mapping |
| responseId | `string` |  to be filled if the current response is an edit/update to a previous one |
| isEdit | `boolean` |  denotes if the current response is an edit/update to a previous one |
| showInChatCanvas | `boolean` |  denotes if a separate chat card needs to be created for this response or not |
| isAnonymous | `boolean` |  denotes if the response should be registered as anonymous or not |

**Returns:** `void`

___
<a id="sumbitformresponsewithoutdismiss"></a>

###  sumbitFormResponseWithoutDismiss

▸ **sumbitFormResponseWithoutDismiss**(questionToAnswerMap: *`JSON`*, responseId: *`string`*, isEdit: *`boolean`*, showInChatCanvas: *`boolean`*, isAnonymous: *`boolean`*): `void`

*Defined in FormAPIs.ts:294*

Submits a new response against the form associated with the conversation card This won't dismiss the current screen
*__category__*: response

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| questionToAnswerMap | `JSON` |  question id to answer mapping |
| responseId | `string` |  to be filled if the current response is an edit/update to a previous one |
| isEdit | `boolean` |  denotes if the current response is an edit/update to a previous one |
| showInChatCanvas | `boolean` |  denotes if a separate chat card needs to be created for this response or not |
| isAnonymous | `boolean` |  denotes if the response should be registered as anonymous or not |

**Returns:** `void`

___
<a id="updateactioninstancelocaldatacacheasync"></a>

###  updateActionInstanceLocalDataCacheAsync

▸ **updateActionInstanceLocalDataCacheAsync**(actionProperties: *[KASActionProperties](../classes/kasclient.kasactionproperties.md)*, callback: *`function`*): `void`

*Defined in FormAPIs.ts:832*

Updates/saves the given ActionInstance Properties to the local data cache These properties are stored at an action instance level. So each action instance can save some local data in the cache and it will only be accessible by that particular instance
*__category__*: summary

*__warning__*: This API doesn't work as expected in case of historical messages.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| actionProperties | [KASActionProperties](../classes/kasclient.kasactionproperties.md) |  ActionInstance/Form Properties to be updated/saved |
| callback | `function` |  with below parameters:*   *   *   @param {boolean} success indicates if the update is successful or not*   *   *   @param {string} error json string for the KASError object containing error code and/or description. |

**Returns:** `void`

___
<a id="updateactionpackagelocaldatacacheasync"></a>

###  updateActionPackageLocalDataCacheAsync

▸ **updateActionPackageLocalDataCacheAsync**(actionPackageProperties: *[KASActionPackageProperties](../classes/kasclient.kasactionpackageproperties.md)*, callback: *`function`*): `void`

*Defined in FormAPIs.ts:795*

Updates/saves the given Action Package Properties to the local data cache These properties are saved at the action package level. So the data is shared among all action instances created from this action package.
*__category__*: summary

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| actionPackageProperties | [KASActionPackageProperties](../classes/kasclient.kasactionpackageproperties.md) |  Action Package Properties to be updated/saved |
| callback | `function` |  with below parameters:*   *   *   @param {boolean} success indicates if the update is successful or not*   *   *   @param {string} error json string for the KASError object containing error code and/or description. |

**Returns:** `void`

___
<a id="updateform"></a>

###  updateForm

▸ **updateForm**(fields: *`string`*, shouldInflate: *`boolean`*, callback: *`function`*): `void`

*Defined in FormAPIs.ts:103*

use for making changes in form fields like title, description and settings.
*__category__*: creation

**Parameters:**

| Name | Type |
| ------ | ------ |
| fields | `string` |
| shouldInflate | `boolean` |
| callback | `function` |

**Returns:** `void`

___
<a id="updateformpropertiesasync"></a>

###  updateFormPropertiesAsync

▸ **updateFormPropertiesAsync**(propertyUpdates: *[KASFormPropertyUpdateInfo](../classes/kasclient.kasformpropertyupdateinfo.md)[]*, notifyUsers: *`string`[]*, notificationMessage: *`string`*, callback: *`function`*): `void`

*Defined in FormAPIs.ts:748*

Post a request to update the properties associated with the form
*__category__*: summary

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| propertyUpdates | [KASFormPropertyUpdateInfo](../classes/kasclient.kasformpropertyupdateinfo.md)[] |  an array of all update infos that are needed to be performed, update infos can be created using KASFormPropertyUpdateFactory |
| notifyUsers | `string`[] |  send push notifications to these user ids regarding this update |
| notificationMessage | `string` |  push notification message |
| callback | `function` |  with below parameters:*   @param {boolean} success indicates if the update is successful or not |

**Returns:** `void`

___

