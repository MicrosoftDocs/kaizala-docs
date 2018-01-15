```typescript
class KASForm {
  // Form id, shouldn't be changed
  public id: string;
  // Associated conversation id, shouldn't be changed
  public conversationId: string;
  // Package id of the MiniApp, shouldn't be changed
  public packageId: string;
  // User id who created the form, shouldn't be changed
  public creatorId: string;
  // Form title
  public title: string;

  // If the form is anonymous, default is false
  public isAnonymous: boolean;

  // Expiry time of the form
  public expiry: number;

  // Version of the form, default value is 2, shouldn't be changed
  public version: number;

  // Who can see the summary of the form, default value is All
  public visibility: KASFormResultVisibility;

  // Denotes if multiple responses from a user are allowed or not, default is false
  public isResponseAppended: boolean;

  // Denotes if participants' location is attached with the response or not, default is false
  public isLocationRequested: boolean;

  // Type of the form, default is 20, shouldn't be changed
  public type: number;
  // All the questions associated with the form
  public questions: KASQuestion[];
  // A list of metadata associated with the form
  public properties: KASFormProperty[];
}
```