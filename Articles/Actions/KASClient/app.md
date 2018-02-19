#   App APIs:

| **API** | Description | Request Parameter | Response Output |
| :---: | :---: | :---: | :--- |
| **getUsersDetailsAsync** | Gets users' details (name, pic, phone number, etc.) against their ids | userIds array of user ids | *JSON of user info* |
| **showContactPickerAsync** | Shows a native contact picker, and returns an array of all the selected users' detail | <ul><li>*title of Contact Picker*</li><li>*selectedMutableUser* - array of selected userIds</li><li>*selectedImmutableUser* - array of fixed selected userIds</li><li>*isSingleSelection* - single selection in Contact Picker</li></ul> | Array of all the selected users' details (*Array of JSON*) |
| **showImagePickerAsync** | Shows a native image picker, and returns the selected image path | | *Selected image location* |
| **showAttachmentPickerAsync** | Displays an attachment picker in the native layer | <ul><li>*supportedTypes* - array of supported attachment types for the picker</li><li>additional props to configure the picker</li></ul> | |
| **downloadAttachmentAsync** | Download the attachment specified | <ul><li>*attachment with a valid server path to download*</li><li>callback on download completion</li></ul> | |
| **cancelAttachmentDownloadAsync** | Cancel a download operation queued for an attachment | attachment | |
| **showPlacePickerAsync** | Shows a native place picker, and returns the selected place (lt, lg, n) | Selected location | Latitude/longitude |
| **showLocationOnMap** | Opens up native maps with given location | [KASLocation](KASLocation.md) type | |
| **showDurationPickerAsync** | Shows a native duration picker with day/hour/minute | Default duration to be shown on picker | |
| **isTalkBackEnabledAsync** | Gets whether talkback is enabled or not | | Boolean |
| **generateUUIDAsync** | Gets the new UUID | | Newly generated uuid |
| **getCurrentDeviceLocationAsync** | Gets the current device location | | |
| **getAppLocaleAsync** | Gets the current app locale -language in which the app is rendered, useful for localizing Action's strings | | Locale |
| **getConversationParticipantsCountAsync** | Gets all the participant-ids of the current conversation | | Count of participants |
| **getConversationNameAsync** | Gets the current conversation name | | Name of the conversation |
| **dismissCurrentScreen** | Dismiss the current screen (Creation, Response, or Summary) | | |
| **showProgressBar** | Shows a native full sreen progress bar with the given text | Text to display | |
| **hideProgressBar** | Hides the current progress bar, if any | | |
| **getCurrentUserIdAsync** | Gets the current user id who has opened the Action | | User ID |
| **showImageImmersiveView** | Shows Image in Immersive view | Array of images url | |
| **openAttachmentImmersiveView** | Open attachment in Immersive view | Attachment object | |
| **hasStorageAccessForAttachmentType** | checks whether app has read/write access to the storage | Attachment type | |
| **generateBase64ThumbnailAsync** | Generates Base64 thumbnail for an image | localPath for the imageAttachment whose thumbnail needs to be generated | |
| **getFontSizeMultiplierAsync** | Gets the font size multiplier for large text -	Current only required by iOS | | |
| **getLocalizedStringsAsync** | Gets the localized strings' dictionary based on current app locale | Strings must be provided inside the package with names like: strings_en.json, strings_hi.json, etc.	 | Strings JSON |
| **logToReport** | Logs an error for "Send report" | Attachment type | |
| **isCurrentUserO365SubscribedAsync** | Checks if the current user an O365 subscriber | | Boolean |
| **registerHardwareBackPressCallback** | Registers a callback to be executed on hardware back button press (for Android) | | |
| **initLocalizationStringsAsync** | Initializes the localization strings' map | Dictionary  - the strings' map | Success(Boolean) denotes the success/failure of the initialization |
| **getString** |	Returns a string from the localized strings' file |stringId	||


##  Get user info

```typescript
/**
  * Gets users' details (name, pic, phone number, etc.) against their ids
  * @param {string[]} userIds array of user ids
  * @param {Callback} callback with below parameters:
  * * * * @param {Dictionary<UserId: string, UserInfo: KASUser>} userIdToInfoMap (users' details against their ids) can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getUsersDetailsAsync(userIds: string[], callback: function(userIdToInfoMap: {}, error: string))
```

##  Show contact picker

```typescript
/**
  * Shows a native contact picker, and returns an array of all the selected users' details
  * @param {Callback} callback with below parameters:
  * * * * @param {KASUser[]} selectedUsers (array of user details) can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function showContactPickerAsync(callback: function(users: KASUser[], error: string))
```

##  Show image picker

```typescript
/**
  * Shows a native image picker, and returns the selected image path
  * @param {Callback} callback with below parameters:
  * * * * @param {string} selectedImagePath can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function showImagePickerAsync(callback: function(selectedImagePath: string, error: string))
```

##  Get current device location

```typescript
/**
  * Gets the current device location
  * @param {Callback} callback with below parameters:
  * * * * @param {string} location can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getCurrentDeviceLocationAsync(callback: function(location: string, error: string))
```

##  Place picker

```typescript
/**
  * Shows a native place picker, and returns the selected place (lt, lg, n)
  * @param {Callback} callback with below parameters:
  * * * * @param {KASLocation} selectedLocation can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function showPlacePickerAsync(callback: (selectedLocation: KASLocation, error: string))
```

##  Show location on maps

```typescript
/**
  * Opens up native maps with a marker at selected location(KASLocation type)
  * @param {KASLocation} selectedLocation
  */
  function showLocationOnMap(selectedLocation: KASLocation)
```

##  Show error message (alert or toast)

```typescript
/**
  * Shows a native alert (for iOS) or a toast (for Android) with the message
  * @param {string} message
  */
  function showNativeErrorMessage(message: string)
```

##  Get current language used by the app

```typescript
/**
  * Gets the current app locale, the language in which the app is rendered, useful for localizing MiniApp's strings
  * @param {Callback} callback with below parameters:
  * * * * @param {string} locale can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getAppLocaleAsync(callback: function(locale: string, error: string))
```

##  Get the name of the current conversation

```typescript
/**
  * Gets the current conversation name
  * @param {Callback} callback with below parameters:
  * * * * @param {string} name can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getConversationNameAsync(callback: function(name: string, error: string))
```

##  Dismiss the currently opened Action's screen

```typescript
/**
  * Dismiss the current screen (Creation, Response, or Summary)
  */
  function dismissCurrentScreen()
```

##  Show native progress bar

```typescript
/**
  * Shows a native full sreen progress bar with the given text
  * @param {string} text
  */
  function showProgressBar(text: string)
```

##  Hide native progress bar

```typescript
/**
  * Hides the current progress bar, if any
  */
  function hideProgressBar()
```

##  Get current user id

```typescript
/**
  * Gets the current user id who has opened the MiniApp
  * @param {Callback} callback with below parameters:
  * * * * @param {string} userId can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getCurrentUserIdAsync(callback: function(userId: string, error: string))
```

##  Register for hardware back button press (Android)

```typescript
/**
  * Registers a callback to be executed on hardware back button press (for Android)
  * @param {Callback} callback to be executed
  */
  function registerHardwareBackPressCallback(callback: function())
```

##  Localization for Action

```typescript
/**
  * Gets the localized strings' dictionary based on current app locale.
  * Strings must be provided inside the package with names like: strings_en.json, strings_hi.json, etc.
  * @param {Callback} callback with below parameters:
  * * * * @param {JSON} strings can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function getLocalizedStringsAsync(callback: (strings: JSON, error: string))
```

##  printf() for Action

```typescript
/**
  * Returns a string.
  * @param {string} string denotes the formatted string. Specifier should be mentioned like {0},{1},{2}.....
  * @param {string[]} args array of arguments.
  */
  function printf(main: string, ...args: any[]): string
```
