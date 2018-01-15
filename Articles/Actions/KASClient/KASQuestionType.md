```typescript
enum KASQuestionType {
  // Default type
  None = -1,
  // Only one option can be selected from the list of options
  SingleSelect = 0,
  // Multiple options can be selected from the list of options
  MultiSelect = 1,
  // Any text can be the answer to the question
  Text = 2,
  // Only numbers can be a valid answer to the question
  Numeric = 3,
  // User's current location will be attached as the answer
  Location = 4,

  // Date time type answer
  DateTime = 5,

  // Answer will be an image attachment
  Image = 6,
  // Single select type, but each question's options are dependent upon the choice of the previous one
  SingleSelectExternal = 7
}
```
