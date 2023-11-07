---
description: Master Microsoft's KASClient Form module with this comprehensive guide. Learn to create, update, and manage forms, handle responses, and more.
---
[](../README.md) > [KASClient](../modules/kasclient.md) > [Form](../modules/kasclient.form.md)

# Module: Form

## Index

### Creation

* [initFormAsync](kasclient.form.md#initformasync)
* [submitFormRequestV2](kasclient.form.md#submitformrequestv2)
* [submitFormRequestWithoutDismiss](kasclient.form.md#submitformrequestwithoutdismiss)
* [updateForm](kasclient.form.md#updateform)
### Response

* [canRespondToFormAsync](kasclient.form.md#canrespondtoformasync)
* [getFormAsync](kasclient.form.md#getformasync)
* [getFormStatusAsync](kasclient.form.md#getformstatusasync)
* [getMyFormResponsesAsync](kasclient.form.md#getmyformresponsesasync)
* [sumbitFormResponse](kasclient.form.md#sumbitformresponse)
* [sumbitFormResponseWithoutDismiss](kasclient.form.md#sumbitformresponsewithoutdismiss)
### Summary

* [FormSummaryCallback](kasclient.form.md#formsummarycallback)
* [addCommentOnForm](kasclient.form.md#addcommentonform)
* [closeForm](kasclient.form.md#closeform)
* [copyFormAndForward](kasclient.form.md#copyformandforward)
* [executeActionFetchQueryAsync](kasclient.form.md#executeactionfetchqueryasync)
* [fetchFormAsync](kasclient.form.md#fetchformasync)
* [fetchFormInfosAsync](kasclient.form.md#fetchforminfosasync)
* [getActionInstanceLocalDataCacheAsync](kasclient.form.md#getactioninstancelocaldatacacheasync)
* [getActionPackageLocalDataCacheAsync](kasclient.form.md#getactionpackagelocaldatacacheasync)
* [getFormReactionAsync](kasclient.form.md#getformreactionasync)
* [getFormSummaryAsync](kasclient.form.md#getformsummaryasync)
* [getFormURLAsync](kasclient.form.md#getformurlasync)
* [getFormUserCapabilitiesAsync](kasclient.form.md#getformusercapabilitiesasync)
* [isSubscribed](kasclient.form.md#issubscribed)
* [likeForm](kasclient.form.md#likeform)
* [sendRemindersToRespond](kasclient.form.md#sendreminderstorespond)
* [shareFormURL](kasclient.form.md#shareformurl)
* [showAllReactions](kasclient.form.md#showallreactions)
* [updateActionInstanceLocalDataCacheAsync](kasclient.form.md#updateactioninstancelocaldatacacheasync)
* [updateActionPackageLocalDataCacheAsync](kasclient.form.md#updateactionpackagelocaldatacacheasync)
* [updateFormPropertiesAsync](kasclient.form.md#updateformpropertiesasync)

---

## Creation

<a id="initformasync"></a>

###  initFormAsync

▸ **initFormAsync**(callback: *`function`*): `void`

Initializes and returns an empty form object based on the default form file present in the package

#### Sample Usage

```
KASClient.Form.initFormAsync(function (form, error) {
     if (error != null) {
         // use form
     }
});
```

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {KASForm} form can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="submitformrequestv2"></a>

###  submitFormRequestV2

▸ **submitFormRequestV2**(form: *[KASForm](../classes/kasclient.kasform.md)*, shouldDismiss?: *`boolean`*, shouldSendToSubscribers?: *`boolean`*): `void`

Submits the newly created form as a request. This results a new conversation card

**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| form | [KASForm](../classes/kasclient.kasform.md) | - |  \- |
| `Default value` shouldDismiss | `boolean` | false |  true if form needs to be dismissed upon submission; false otherwise |
| `Default value` shouldSendToSubscribers | `boolean` | true |  applicable in public groups, set to false if the request is not intended for subscribers |

**Returns:** `void`

___
<a id="submitformrequestwithoutdismiss"></a>

###  submitFormRequestWithoutDismiss

▸ **submitFormRequestWithoutDismiss**(form: *[KASForm](../classes/kasclient.kasform.md)*, shouldInflate: *`boolean`*): `void`

Submits the newly created form as a request. This results a new conversation card

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| form | [KASForm](../classes/kasclient.kasform.md) |  \- |
| shouldInflate | `boolean` |  Boolean – should inflate/not |

**Returns:** `void`

___
<a id="updateform"></a>

###  updateForm

▸ **updateForm**(fields: *`string`*, shouldInflate: *`boolean`*, callback: *`function`*): `void`

use for making changes in form fields like title, description and settings.

#### Sample Usage

```
  var fieldsToUpdate = {"title" : "<updated title", "exp" : "<expiry time>",
           "vis" : "<result visibility - set as sender/all/admin>", "Description": "<Updated survey desc>"};
  KASClient.Form.updateForm(JSON.stringify(fieldsToUpdate), false, function(success) {
       if(success) {
         //do something
       }
   });
```

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| fields | `string` |  json string of fields that require updation |
| shouldInflate | `boolean` |  Boolean – should inflate/not |
| callback | `function` |  with below params:<br><br>\* @param {boolean} success true if update was successful; false otherwise |

**Returns:** `void`

___

## Response

<a id="canrespondtoformasync"></a>

###  canRespondToFormAsync

▸ **canRespondToFormAsync**(callback: *`function`*): `void`

Gets whether the current user can respond to the form

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {boolean} canRespond true if current user is allowed to respond |

**Returns:** `void`

___
<a id="getformasync"></a>

###  getFormAsync

▸ **getFormAsync**(callback: *`function`*): `void`

Gets the form object associated with the conversation card

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {KASForm} form can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="getformstatusasync"></a>

###  getFormStatusAsync

▸ **getFormStatusAsync**(callback: *`function`*): `void`

Gets the status of the form associated with the conversation card

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {boolean} isActive true if the form is not yet expired<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="getmyformresponsesasync"></a>

###  getMyFormResponsesAsync

▸ **getMyFormResponsesAsync**(callback: *`function`*, onlyCurrentResponse?: *`boolean`*): `void`

Gets all the responses of the current user against the form

**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| callback | `function` | - |  with below parameters:<br><br>\* @param {KASFormResponse\[\]} responses can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |
| `Default value` onlyCurrentResponse | `boolean` | true |  Applicable for Response Actions where this method returns only the current response in context, set this flag to false to fetch all the responses instead. Default is true |

**Returns:** `void`

___
<a id="sumbitformresponse"></a>

###  sumbitFormResponse

▸ **sumbitFormResponse**(questionToAnswerMap: *`JSON`*, responseId: *`string`*, isEdit: *`boolean`*, showInChatCanvas: *`boolean`*, isAnonymous: *`boolean`*): `void`

Submits a new response against the form associated with the conversation card This will dismiss the current screen

#### Sample Usage

```
var questionToAnswerMap = { "0": "answer" };
KASClient.Form.sumbitFormResponse(questionToAnswerMap, null, false, false, false);
```

#### Note

```
questionToAnswerMap is a map which has key as question Id and value as the response to the question
Say question of id 1 is of type "Text" which means it takes string as response. You should define it like {1: "<answer>"}
```

Response value for _[KASQuestionType](../enums/kasclient.kasquestiontype.md)_ should be:
*   **Single Select** : Option id (String). e.g. "1"
*   **MultiSelect** : Stringified array of option ids. e.g. JSON.stringify(\[1,3\])
*   **Text** : String. e.g. "dummy"
*   **Numeric** : Number. e.g. 543
*   **Location** : Stringified _[KASLocation](../classes/kasclient.kaslocation.md)_ object. e.g. JSON.stringify(location.toJSON()) or JSON.stringify({"lg": 70.4, "lt": 18.6, "n": "address"})
*   **DateTime** : Epoch timestamp in millieseconds. e.g. 1550651524074
*   **Image** : Image path. e.g. "file://imagePath.png"
*   **AttachmentList** : Stringified array of _[KASAttachment](../classes/kasclient.kasattachment.md)_ objects. e.g. JSON.stringify(attachments), attachments is array of KASAttachment
*   **PhoneNumber** : Stringified _[KASPhoneNumber](../classes/kasclient.kasphonenumber.md)_ object. e.g. SON.stringify(phoneNumber.toJSON()) or JSON.stringify({"cc": "+91", "pn": "98XXXXXXX6"})
*   **DateOnly** : Date string (YYYY-MM-DD). e.g. "2019-04-17"

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

Submits a new response against the form associated with the conversation card This won't dismiss the current screen

#### Sample Usage

```
var questionToAnswerMap = { "0": "answer" };
KASClient.Form.sumbitFormResponseWithoutDismiss(questionToAnswerMap, null, false, false, false);
```

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| questionToAnswerMap | `JSON` |  question id to answer mapping (See _[sumbitFormResponse](kasclient.form.md#sumbitformresponse)_ for details) |
| responseId | `string` |  to be filled if the current response is an edit/update to a previous one |
| isEdit | `boolean` |  denotes if the current response is an edit/update to a previous one |
| showInChatCanvas | `boolean` |  denotes if a separate chat card needs to be created for this response or not |
| isAnonymous | `boolean` |  denotes if the response should be registered as anonymous or not |

**Returns:** `void`

___

## Summary

<a id="formsummarycallback"></a>

###  FormSummaryCallback

**Ƭ FormSummaryCallback**: *`function`*

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
<a id="addcommentonform"></a>

###  addCommentOnForm

▸ **addCommentOnForm**(comment: *`string`*): `void`

Requests to add a comment to a form

**Parameters:**

| Name | Type |
| ------ | ------ |
| comment | `string` |

**Returns:** `void`

___
<a id="closeform"></a>

###  closeForm

▸ **closeForm**(): `void`

Closes the form associated with the card, no responses will be allowed further

**Returns:** `void`

___
<a id="copyformandforward"></a>

###  copyFormAndForward

▸ **copyFormAndForward**(): `void`

Launches the conversation picker to forward a copy of the existing form as a new conversation card

**Returns:** `void`

___
<a id="executeactionfetchqueryasync"></a>

###  executeActionFetchQueryAsync

▸ **executeActionFetchQueryAsync**(formId: *`string`*, fetchJsonQueryId: *`string`*, fetchJsonQueryParams: *`JSON`*, callback: *`function`*): `void`

Retrieves Action instance (or form) rows/responses using FetchJson query (SQL in JSON format). Using this api, one can execute rich queries on all the rows and get detailed or summary as result. These queries need to be mentioned in Action's appModel to allow Action developers to have query level permissions. One can execute such a query with just the query id, and the required placeholder values, if any.
#### Note

1.  Action instance column/question ids will be used as attribute ids of the FetchJson query
2.  Output will be list of rows, each row containing column id-value pairs

#### Sample Usage

```
// AppModel questions: ResponderName (0) | City (1) | FavoriteMovie (2)
// Query (q123): SELECT question0 WHERE question1="@param1" AND question2="@param2"
// To fetch responders from "Mumbai" whose favorite movie is "Harry Potter"
var params = { "@param1": "Mumbai", "@param2": "Harry Potter"};
KASClient.Form.executeActionFetchQueryAsync("XXXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX", "q123", params, function (result, error) {
   if (!error) {
       for (var i = 0; i < result.rows.length; i++) {
           var row = result.rows[i];
           console.log("Responder name: " + row["0"]);
       }
   }
});
```

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| formId | `string` |  Action instance (or form) id whose rows need to be fetched |
| fetchJsonQueryId | `string` |  FetchJson query id (mentioned in the Action package) |
| fetchJsonQueryParams | `JSON` |  Map of query parameter placeholders to values |
| callback | `function` |  with below parameters:<br><br>\* @param {JSON} fetchJsonResult - The FetchJson query result<br><br>\* @param {string} error json string for the KASError object containing error code and/or description. |

**Returns:** `void`

___
<a id="fetchformasync"></a>

###  fetchFormAsync

▸ **fetchFormAsync**(formId: *`string`*, callback: *`function`*): `void`

Retrieves an Action instance (or form) for the given id. It first tries to get the instance locally, then fetches it from server as fallback.
#### Note

An Action can fetch instances of itself or another Action which belong to its own appGroup

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| formId | `string` |  Id of the instance to be fetched |
| callback | `function` |  with below parameters:<br><br>\* @param {KASForm} form - Action instance (or form)<br><br>\* @param {string} error json string for the KASError object containing error code and/or description. |

**Returns:** `void`

___
<a id="fetchforminfosasync"></a>

###  fetchFormInfosAsync

▸ **fetchFormInfosAsync**(request: *[KASFormInfoRequest](../classes/kasclient.kasforminforequest.md)*, callback: *`function`*): `void`

Retrieves Action instance (or form) informations of an Action package. This is useful in cross Action data access, where one Action can fetch the rows/responses of instance of another Action - this api is used to fetch the instance id required to fetch rows.
#### Note

An Action can fetch instances of itself or another Action which belong to its own appGroup

#### Sample Usage

```
var request = new KASClient.KASFormInfoRequest();
request.packageId = "some-package-id";
request.scopeId = "XXXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX"; // Group id

KASClient.Form.fetchFormInfosAsync(request, function (response, error) {
   if (!error) {
       for (var i = 0; i < response.formInfos.length; i++) {
           var formInfo = response.formInfos[i]; // KASFormInfo
           console.log("Instance id: " + formInfo.id);
           console.log("Instance title: " + formInfo.title);
       }
   }
})
```

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| request | [KASFormInfoRequest](../classes/kasclient.kasforminforequest.md) |  Request containing api parameters |
| callback | `function` |  with below parameters:<br><br>\* @param {KASFormInfoResponse} response - Response containing Action instance (or form) infos<br><br>\* @param {string} error json string for the KASError object containing error code and/or description. |

**Returns:** `void`

___
<a id="getactioninstancelocaldatacacheasync"></a>

###  getActionInstanceLocalDataCacheAsync

▸ **getActionInstanceLocalDataCacheAsync**(callback: *`function`*): `void`

Retrieves the ActionInstance Properties from the local data cache if any exists These properties are stored at an action instance level. So the local data saved for the particular action instance will be returned by this API.
#### Note

This API doesn't work as expected in case of historical messages.

#### Sample Usage

```
KASClient.Form.getActionInstanceLocalDataCacheAsync(function (actionPackageProperties, error) {
     if (error == null && actionPackageProperties != null && actionPackageProperties.properties) {
          if (actionPackageProperties.properties.hasOwnProperty("prop1") {
             console.log(actionPackageProperties.properties["prop1"]);
          }
     }
 });
```

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {KASActionProperties} actionProperties ActionInstance/Form Properties<br><br>\* @param {string} error json string for the KASError object containing error code and/or description. |

**Returns:** `void`

___
<a id="getactionpackagelocaldatacacheasync"></a>

###  getActionPackageLocalDataCacheAsync

▸ **getActionPackageLocalDataCacheAsync**(callback: *`function`*): `void`

Retrieves the Action Package Properties from the local data cache if any exists These properties are saved at the action package level. So all action instances created from this action package will receive the same data.
#### Note

This API doesn't work as expected in case of historical messages.

#### Sample Usage

```
KASClient.Form.getActionPackageLocalDataCacheAsync(function (actionPackageProperties, error) {
     if (error == null && actionPackageProperties != null && actionPackageProperties.properties) {
          if (actionPackageProperties.properties.hasOwnProperty("prop1") {
             console.log(actionPackageProperties.properties["prop1"]);
          }
     }
 });
```

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {KASActionPackageProperties} actionPackageProperties Action Package Properties<br><br>\* @param {string} error json string for the KASError object containing error code and/or description. |

**Returns:** `void`

___
<a id="getformreactionasync"></a>

###  getFormReactionAsync

▸ **getFormReactionAsync**(callback: *`function`*): `void`

Gets the consolidated reaction (likes and comments) of the conversation card associated with the form

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {KASFormReaction} reaction can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="getformsummaryasync"></a>

###  getFormSummaryAsync

▸ **getFormSummaryAsync**(mostUpdatedCallback: *[FormSummaryCallback](kasclient.form.md#formsummarycallback)*, notifyCallback: *[FormSummaryCallback](kasclient.form.md#formsummarycallback)*): `void`

Gets flat responses by all the users, and processed summary from all the responses associated with the form. It requires two callbacks:
#### Note

This is useful when the network is flaky/disconnected, so that summary can immediately be shown with the present data we have, but with an option to refresh it later on arrival of latest data from server! None of the callbacks are mandatory, so if 1st is nil, this method can be used to always fetch summary from server, and if 2nd is nil, this can be used to always fetch summary from local database!

#### Sample Usage

```
KASClient.Form.getFormSummaryAsync(
   // Data fetched from database
   function (flatSummary, processedSummary, error) {
      if (error != null) {
      }
   },
   // Data fetched from server
   function (flatSummary, processedSummary, error) {
      if (error != null) {
      }
   })
```

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| mostUpdatedCallback | [FormSummaryCallback](kasclient.form.md#formsummarycallback) |  to immediately get the most updated summary from local database. It has below parameters:<br><br>\* @param {KASFormFlatSummary} flatSummary can be null in case of error<br><br>\* @param {KASFormProcessedSummary} processedSummary can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |
| notifyCallback | [FormSummaryCallback](kasclient.form.md#formsummarycallback) |  to get notified with the latest summary fetched from server. It has below parameters:<br><br>\* @param {KASFormFlatSummary} flatSummary can be null in case of error<br><br>\* @param {KASFormProcessedSummary} processedSummary can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="getformurlasync"></a>

###  getFormURLAsync

▸ **getFormURLAsync**(callback: *`function`*): `void`

Gets the file url from server containing flat responses associated with the form

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {string} url can be null in case of error<br><br>\* @param {string} error message in case of error, null otherwise |

**Returns:** `void`

___
<a id="getformusercapabilitiesasync"></a>

###  getFormUserCapabilitiesAsync

▸ **getFormUserCapabilitiesAsync**(callback: *`function`*): `void`

Gets form permissions

#### Sample Usage

```
KASClient.Form.getFormUserCapabilitiesAsync(function (permissions, error) {
    if(!error) {
        canRespond = permissions.canRespond;
        canSendReminder = permissions.canSendReminder;
        shouldSeeSummary = permissions.shouldSeeSummary;
    }
});
```

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {KASFormUserCapabilities} permissions<br><br>\* @param {string} error error string in case of error; null otherwise |

**Returns:** `void`

___
<a id="issubscribed"></a>

###  isSubscribed

▸ **isSubscribed**(callback: *`function`*): `void`

Gets whether the current user is subscriber or not

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| callback | `function` |  with below parameters:<br><br>\* @param {boolean} isSubscribed true if current user subscriber |

**Returns:** `void`

___
<a id="likeform"></a>

###  likeForm

▸ **likeForm**(): `void`

Requests to add a like count to a form, the count may decrease if the current user has already liked the form

**Returns:** `void`

___
<a id="sendreminderstorespond"></a>

###  sendRemindersToRespond

▸ **sendRemindersToRespond**(): `void`

Sends a reminder (a new conversation card) against the existing card

**Returns:** `void`

___
<a id="shareformurl"></a>

###  shareFormURL

▸ **shareFormURL**(url: *`string`*): `void`

Share the result url fetched from server - Launches native share screen for the form url

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| url | `string` |  to be shared |

**Returns:** `void`

___
<a id="showallreactions"></a>

###  showAllReactions

▸ **showAllReactions**(showComments?: *`boolean`*): `void`

Shows all the reaction screen (likes and comments) against the form

**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| `Default value` showComments | `boolean` | true |  true if comments also need to be shown; false otherwise |

**Returns:** `void`

___
<a id="updateactioninstancelocaldatacacheasync"></a>

###  updateActionInstanceLocalDataCacheAsync

▸ **updateActionInstanceLocalDataCacheAsync**(actionProperties: *[KASActionProperties](../classes/kasclient.kasactionproperties.md)*, callback: *`function`*): `void`

Updates/saves the given ActionInstance Properties to the local data cache These properties are stored at an action instance level. So each action instance can save some local data in the cache and it will only be accessible by that particular instance

#### Sample Usage

```
var actionPackageProperties = KASClient.KASActionPackageProperties.fromJSON(JSON.parse("{}"));
actionPackageProperties.properties = JSON.parse("{}");
actionPackageProperties.properties[prop1] = value1;
KASClient.Form.updateActionInstanceLocalDataCacheAsync(actionPackageProperties, function(success, error) {
     if(!error) {
     }
});
```
#### Note

This API doesn't work as expected in case of historical messages.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| actionProperties | [KASActionProperties](../classes/kasclient.kasactionproperties.md) |  ActionInstance/Form Properties to be updated/saved |
| callback | `function` |  with below parameters:<br><br>\* @param {boolean} success indicates if the update is successful or not<br><br>\* @param {string} error json string for the KASError object containing error code and/or description. |

**Returns:** `void`

___
<a id="updateactionpackagelocaldatacacheasync"></a>

###  updateActionPackageLocalDataCacheAsync

▸ **updateActionPackageLocalDataCacheAsync**(actionPackageProperties: *[KASActionPackageProperties](../classes/kasclient.kasactionpackageproperties.md)*, callback: *`function`*): `void`

Updates/saves the given Action Package Properties to the local data cache These properties are saved at the action package level. So the data is shared among all action instances created from this action package.

#### Sample Usage

```
var actionPackageProperties = KASClient.KASActionPackageProperties.fromJSON(JSON.parse("{}"));
actionPackageProperties.properties = JSON.parse("{}");
actionPackageProperties.properties[prop1] = value1;
KASClient.Form.updateActionPackageLocalDataCacheAsync(actionPackageProperties, function(success, error) {
     if(!error) {
     }
});
```
#### Note

This API doesn't work as expected in case of historical messages.

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| actionPackageProperties | [KASActionPackageProperties](../classes/kasclient.kasactionpackageproperties.md) |  Action Package Properties to be updated/saved |
| callback | `function` |  with below parameters:<br><br>\* @param {boolean} success indicates if the update is successful or not<br><br>\* @param {string} error json string for the KASError object containing error code and/or description. |

**Returns:** `void`

___
<a id="updateformpropertiesasync"></a>

###  updateFormPropertiesAsync

▸ **updateFormPropertiesAsync**(propertyUpdates: *[KASFormPropertyUpdateInfo](../classes/kasclient.kasformpropertyupdateinfo.md)[]*, notifyUsers: *`string`[]*, notificationMessage: *`string`*, callback: *`function`*, shouldSendToSubscribers?: *`boolean`*): `void`

Post a request to update the properties associated with the form

#### Sample Usage

```
var updateProperties = [];
var currentFormProperty = new KASClient.KASFormProperty(); // type: KASFormProperty
currentFormProperty.name = "<name>";
currentFormProperty.value = "<value>";
var property1ToAdd = KASClient.KASFormPropertyUpdateFactory.addProperty(currentFormProperty); //use updateValueInProperty in case of existing form property
updateProperties.push(property1ToAdd);
var notifyUsersList = [];
// notifyUsersList.push(<"uid1">);
// notifyUsersList.push("<uid2>");
KASClient.Form.updateFormPropertiesAsync(updateProperties, notifyUsersList, notificationMessage, function (success) {
  if (success) {
  }
});
```

**Parameters:**

| Name | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| propertyUpdates | [KASFormPropertyUpdateInfo](../classes/kasclient.kasformpropertyupdateinfo.md)[] | - |  an array of all update infos that are needed to be performed, update infos can be created using KASFormPropertyUpdateFactory |
| notifyUsers | `string`[] | - |  send push notifications to these user ids regarding this update |
| notificationMessage | `string` | - |  push notification message |
| callback | `function` | - |  with below parameters:<br><br>\* @param {boolean} success indicates if the update is successful or not |
| `Default value` shouldSendToSubscribers | `boolean` | false |  Optional field (default is false) only applicable in public groups. If set to true, then the property updates will reach subscribers too in a public group. |

**Returns:** `void`

___

