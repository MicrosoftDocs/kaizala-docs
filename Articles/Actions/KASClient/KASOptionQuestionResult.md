```typescript
class KASOptionQuestionResult extends KASQuestionResult {
  // For SingleSelect/MultiSelect question, the result will be option id versus their counts
  // Dictionary<OptionId: number, OptionResult: KASOptionResult>
  public optionResults;
  /**
  * Gets all the option ids sorted in their total responses count (descending)
  * @return {number[]} list of all the option ids
  */
  public getResultsOrder(): number[];
}
```

