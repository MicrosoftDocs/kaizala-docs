---
title: /Action Details
description: Reference Article for API to query regarding details of Kaizala Actions
topic: Reference
author: nitinjms
---
### GET /actions/{actionId}/

Check-out the API for retrieving the list of action instances sent to a group using the [API for get /actions here](actions_get.md). You can retrieve further details about a specific action instance referenced by an actionId.

    GET {endpoint-url}/v1/groups/{groupId}/actions/{actionId}/

#### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| URL Path Parameter | groupId | String | No | GUID representing the groupId of the specific group resource |
| URL Path Parameter | actionId | String | No | GUID representing the specific action instance |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |
| URL Query Parameter | getDetails | Boolean | Yes | Use to get drill-down details of the specific action; Default is False |

#### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| actionType | String | Type of action being returned |
| actionDetails | JSON object | JSON onbject specific to the actiontype |
| sender | String | Phone number of the user who sent the action to the group |
| sentAt | DateTime | Time when the action was posted to the group |

#####  actionDetails object structure for the action 'Job':

| Parameter | Type | Description |
| :---: | :---: | :--- |
| dueDate | DateTime | Due date for the Job |
| title | String | Title of the Job |
| status | Boolean | True when all assignees have completed the job |
| responseCount | Numeric | Number of assignees who have marked the job complete |
| assigneeCount | Numeric | Number of assignees |
| responses | JSON Array | JSON Array of individual Job responses |

#####  actionDetails object structure for the action 'Survey':

| Parameter | Type | Description |
| :---: | :---: | :--- |
| actionId | String | GUID representing the specific action instance |
| title | String | Title of the Survey |
| responseCount | Numeric | Number of people who responded to the Survey |
| expiryDate | DateTime | DateTime of the Survey expiry time |

###### Sample JSON Response:

```javascript
{
  "actions": [
    {
      "referenceId": "88a93ddd-0349d-4d18-86ee-c0f8484728db",
      "actionType": "Survey",
      "sender": "+91960000",
      "creationTime": 1480931759,
      "actionBody": {
        "actionId": "8106b2bb-236c-4952-a554-2baadcbd49a0",
        "title": "Sample Survey",
        "responseCount": 1
      }
    }
]
}
```
