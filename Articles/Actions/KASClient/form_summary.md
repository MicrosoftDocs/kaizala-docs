#   Form summary flow APIs:

| **API** | Description | Request Parameter | Response Output |
| :---: | :---: | :---: | :--- |
| **shouldSeeFormSummaryAsync** | Gets whether the form summary is visible to the current user |  | *shouldSeeSummary (boolean)* - true if current user is allowed to see summary |
| **getFormSummaryAsync** | Gets responses by all the users, and processed summary from all the responses associated with the form | Involves flat form summary callback and processed form summary callback | Summary objects |
| **getFlatFormSummaryAsync** | Gets flat responses by all the users associated with the form (It is advised to use getFormSummary() instead of this) | | *flatSummary* – summary object |
| **getProcessedFormSummaryAsync** | Gets processed summary from all the responses associated with the form (It is advised to use getFormSummary() instead of this) | | *processedSummary* – summary object |
| **getAggregatedFormSummaryAsync** | Gets aggregated summary from all the responses associated with the form | | *aggregatedSummary* – summary object |
| **getFormURLAsync** | Gets the file url from server containing flat responses associated with the form | | Url |
| **shareFormURL** | Launches native share screen for the form url | Url to be shared | |
| **getFormReactionAsync** | Gets the consolidated reaction (likes and comments) of the conversation card associated with the form | | Reaction object |
| **showAllReactions** | Shows all the reaction screen (likes and comments) against the form | | |
| **likeForm** | Requests to add a like count to a form, the count may decrease if the current user has already liked the form | | |
| **addCommentOnForm** | Requests to add a comment to a form | | |
| **respondToForm** | Requests to add a response to a form, by launching response screen | | |
| **sendRemindersToRespond** | Sends a reminder (a new conversation card) against the existing card | | |
| **copyFormAndForward** | Launches the conversation picker to forward a copy of the existing form as a new conversation card | | |
| **updateFormPropertiesAsync** | Post a request to update the properties associated with the form |  <ul><li>*propertyUpdates* - an array of all update infos that are needed to be performed – *array of KASFormPropertyUpdateInfo*</li><li>*notifyUsers* - send push notifications to these user ids regarding this update – *array of strings*</li><li>*notificationMessage* - push notification message *string*</li></ul> | *Success(Boolean)* - denotes the success/failure of the update|

##   Get the summary associated with the Form

```typescript 
/**
  * Gets flat responses by all the users, and processed summary from all the responses associated
  * with the form. It requires two callbacks:
  * @param {Callback} mostUpdatedCallback to immediately get the most updated summary from local database. It has below parameters:
  * * * * @param {KASFormFlatSummary} flatSummary can be null in case of error
  * * * * @param {KASFormProcessedSummary} processedSummary can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  * @param {Callback} notifyCallback to get notified with the latest summary fetched from server. It has below parameters:
  * * * * @param {KASFormFlatSummary} flatSummary can be null in case of error
  * * * * @param {KASFormProcessedSummary} processedSummary can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  *
  * This is useful when the network is flaky/disconnected, so that summary can
  * immediately be shown with the present data we have, but with an option to refresh
  * it later on arrival of latest data from server! None of the callbacks are mandatory,
  * so if 1st is nil, this method can be used to always fetch summary from server, and
  * if 2nd is nil, this can be used to always fetch summary from local database!
  */
  function getFormSummaryAsync(mostUpdatedCallback: function(flatSummary: KASFormFlatSummary, processedSummary: KASFormProcessedSummary, error: string),
			       notifyCallback: function(flatSummary: KASFormFlatSummary, processedSummary: KASFormProcessedSummary, error: string))
```

##   Get the flat summary (all responses) associated with the Form

```typescript
/**
  * Gets flat responses by all the users associated with the form (It is advised to use getFormSummary() instead of this)
  * @param {Callback} callback with below parameters:
  * * * * @param {KASFormFlatSummary} flatSummary can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getFlatFormSummaryAsync(callback: function(flatSummary: KASFormFlatSummary, error: string))
```

##   Get the processed summary (aggregated responses) associated with the Form

```typescript
/**
  * Gets processed summary from all the responses associated with the form (It is advised to use getFormSummary() instead of this)
  * @param {Callback} callback with below parameters:
  * * * * @param {KASFormProcessedSummary} processedSummary can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getProcessedFormSummaryAsync(callback: function(processedSummary: KASFormProcessedSummary, error: string))
```

##   Fetch (from server) and get the result url (all responses) associated with the Form

```typescript
/**
  * Gets the file url from server containing flat responses associated with the form
  * @param {Callback} callback with below parameters:
  * * * * @param {string} url can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getFormURLAsync(callback: function(url: string, error: string))
```

##   Share the result url fetched from server

```typescript
/**
  * Launches native share screen for the form url
  * @param {string} url to be shared
  */
  function shareFormURL(url: string)
```

##   Get all the reactions associated with the Form

```typescript
/**
  * Gets the consolidated reaction (likes and comments) of the conversation card associated with the form
  * @param {Callback} callback with below parameters:
  * * * * @param {KASFormReaction} reaction can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getFormReactionAsync(callback: function(reaction: KASFormReaction, error: string))
```

##   Show all the reactions associated with the Form

```typescript
/**
  * Shows all the reaction screen (likes and comments) against the form
  */
  function showAllReactions()
```

##   Put a like on the Form (in turn the associated conversation card)

```typescript
/**
  * Requests to add a like count to a form, the count may decrease if the current user has already liked the form
  */
  function likeForm()
```

##   Show response view for the Form

```typescript
/**
  * Requests to add a response to a form, by launching response screen
  */
  function respondToForm()
```

##   Remind other people to respond

```typescript
/**
  * Sends a reminder (a new conversation card) against the existing card
  */
  function sendRemindersToRespond()
```

##   Forward a new Form duplicated from the associated one

```typescript
/**
  * Launches the conversation picker to forward a copy of the existing form as a new conversation card
  */
  function copyFormAndForward() 
```

##   Close the Form (in turn responses to it)

```typescript
/**
  * Closes the form associated with the card, no responses will be allowed further
  */
  function closeForm()
```
