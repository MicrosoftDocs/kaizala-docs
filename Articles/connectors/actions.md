## /actions
API end-point to send/retrieve instances of Kaizala Actions to/from conversation groups inside Kaizala. Current scope is to support following action types:

| Action | GET Supported | POST Supported | Id |
| :---: | :---: | :---: | :---: |
| Picture Attachment | Yes | Yes | image |
| Audio Attachment | No | Yes | audio |
| Document Attachment | No | Yes | document |
| Contact Attachment | No | No | n/a |
| Job | Yes | Yes | job |
| Survey | Yes | Yes | survey |
| Photo with Location | Yes | No | photoWithLocation |
| Let's Meet | No | No | n/a |
| Quick Poll | No | No | n/a |
| Share Location | Yes | No | shareLocation |
| Request Location | No | No | n/a |
| Live Location | No | No | n/a |
| Announcement | No | No | n/a |


*   API to retreive [Actions](actions_get.md) and [Action details](actionDetails.md)
*   [API to post new instances of Actions](actions_post.md)
*   [API to post new action responses/edit existing action responses](action_responses.md)
