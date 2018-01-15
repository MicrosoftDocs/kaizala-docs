```typescript
class KASFormResponse {
  // A unique response id, required in case of updating an existing response
  public id: string;
  // A map for serverUrl against localUrl of all the image attachments to a response
  // Dictionary<ServerUrl: string, LocalUrl: string>
  public serverToLocalAssetUrlMap;
  // A map of question id to answer
  // Dictionary<QuestionId: number, Answer: string>
  public questionToAnswerMap;
}
```