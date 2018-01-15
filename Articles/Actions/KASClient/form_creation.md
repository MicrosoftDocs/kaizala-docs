#   Form creation flow APIs:

| **API** | Description | Request Parameter | Response Output |
| :---: | :---: | :---: | :--- |
| **initFormAsync** | Initializes and returns an empty form object based on the default form file present in the package |  | Form Object |
| **submitFormRequest** | Submits the newly created form as a request. This results a new conversation card | <ul><li>Form</li><li>Boolean – should inflate/not</li></ul>| |
| **submitFormRequestWithoutDismiss** |  |<ul><li>Form</li><li>Boolean – should inflate/not</li></ul>| |
| **updateForm** | Used for making changes in form fields like title, description and settings | <ul><li>Fields that require updation</li><li>Boolean – should inflate/not</li></ul> | |

##  Initialize a Form

```typescript
/**
  * Initializes and returns an empty form object based on the default form file present in the package
  * @param {Callback} callback with below parameters:
  * * * * @param {KASForm} form can be null in case of error
  * * * * @param {string} error message in case of error, null otherwise
  */
  function initFormAsync(callback: function(form: KASForm, error: string))
```

##  Submit the newly created Form

```typescript
/**
  * Submits the newly created form as a request. This results a new conversation card
  * @param {KASForm} form
  */
  function submitFormRequest(form: KASForm)
  ```
