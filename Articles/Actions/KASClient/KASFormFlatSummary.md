```typescript
class KASFormFlatSummary {
  // The id of the associated form, shouldn't be changed
  public formId: string;
  // The id of the associated conversation, shouldn't be changed
  public conversationId: string;

  /**
  * Gets all the user ids who responded to the form
  * @return {string[]} list of all the responded user ids
  */
  public getRespondedUserIds(): string[];

  /**
  * Gets all the responses of a user against a specific question
  * @param {string} userId the unique id of the user
  * @param {string} questionId the id of the question
  * @return {[]} list of all answers given by the user for that question
  */
  public getQuestionResponsesForUserId(userId: string, questionId: number): string[];
  /**
  * Gets all the responses of a user to a form
  * @param {string} userId the unique id of the user
  * @return {Dictionary<QuestionId: number, Answers: Array<string>>} question id to list of answers
  */
  public getResponsesForUserId(userId: string): {};

  /**
  * Gets all the responses of all the users
  * @return {Dictionary<UserId: string, Responses: Array<<Dictionary<QuestionId: string, Answer: string>>>>}
  */
  public getAllResponses(): {};

  /**
  * Gets number of all responses by all users
  * @return {number} number of all responses
  */
  public getTotalResponseCount(): number;
}
```