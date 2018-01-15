#   Form response flow APIs:

| **API** | Description | Request Parameter | Response Output |
| :---: | :---: | :---: | :--- |
| **canRespondToFormAsync** | Gets whether the current user can respond to the form |  | canRespond (Boolean) - true if current user is allowed to respond |
| **getFormAsync** | | | Form object |
| **getFormStatusAsync** | Gets the status of the form associated with the conversation card | | isActive (Boolean) - true if the form is not yet expired |
| **getMyFormResponsesAsync** | Gets all the responses of the current user against the form | | Array of response objects |
| **sumbitFormResponse** | Submits a new response against the form associated with the conversation card – dismisses the current screen |  <ul><li>questionToAnswerMap (JSON ) - question id to answer mapping</li><li>responseId(string) to be filled if the current response is an edit/update to a previous one</li><li>isEdit (boolean) denotes if the current response is an edit/update to a previous one</li><li>showInChatCanvas(Boolean) denotes if a separate chat card needs to be created for this response or not</li><li>isAnonymous(boolean) denotes if the response should be registered as anonymous or not</li></ul> | |
| **sumbitFormResponseWithoutDismiss** | Submits a new response against the form associated with the conversation card without dismissing the current screen |  <ul><li>questionToAnswerMap (JSON ) - question id to answer mapping</li><li>responseId(string) to be filled if the current response is an edit/update to a previous one</li><li>isEdit (boolean) denotes if the current response is an edit/update to a previous one</li><li>showInChatCanvas(Boolean) denotes if a separate chat card needs to be created for this response or not</li><li>isAnonymous(boolean) denotes if the response should be registered as anonymous or not</li></ul> | |


##  Get the associated Form

```typescript
/**
  * Gets the form object associated with the conversation card
  * @param {Callback} callback with below parameters:
  * * * * @param {KASForm} form can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getFormAsync(callback: function(form: KASForm, error: string))
```

##  Check if the associated form is expired or not

```typescript
/**
  * Gets the status of the form associated with the conversation card
  * @param {Callback} callback with below parameters:
  * * * * @param {boolean} isActive true if the form is not yet expired
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getFormStatusAsync(callback: function(isActive: boolean, error: string))
```

##  Get all the responses of the current user

```typescript
/**
  * Gets all the responses of the current user against the form
  * @param {Callback} callback with below parameters:
  * * * * @param {KASFormResponse[]} responses can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getMyFormResponsesAsync(callback: function(responses: KASFormResponse[], error: string))
```

##  Submit a new response for the associated Form

```typescript
/**
  * Submits a new response against the form associated with the conversation card
  * @param {JSON} questionToAnswerMap question id to answer mapping
  * @param {string} responseId to be filled if the current response is an edit/update to a previous one
  * @param {boolean} isEdit denotes if the current response is an edit/update to a previous one
  */
  function sumbitFormResponse(questionToAnswerMap: JSON, responseId: string, isEdit: boolean)
  ```
