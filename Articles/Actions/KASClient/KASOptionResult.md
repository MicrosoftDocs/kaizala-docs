```typescript
class KASOptionResult {
  // Title of the option
  public optionTitle: string;
  // Index of the option
  public optionId: number;
  // How many have chosen this option
  public totalResponsesCount: number;
  // A map of user ids against their response count
  // Dictionary<UserId: string, ResponseCount: number>
  public responderToResponseCount;
}
```

