---
title: /actions
description: Reference Article for API to get list of actions in a group
topic: Reference
author: nitinjms
---
# Get list of Actions in a group
## GET /actions

    GET {endpoint-url}/v1/groups/{groupId}/actions?actionType={action_Type}

### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| URL Path Parameter | groupId | String | No | GUID representing the groupId of the specific group resource |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |
| URL Query Parameter | actionType | String | No | Type of action to retrieve |
| URL Query Parameter | fromDate | DateTime (epoch time) | Yes | Time from which the actions need to be retrieved |
| URL Query Parameter | count | number | Yes | Count of individual actions to be returned; Default = 30 |

### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| actions | JSON Object Array | Array of action objects |
| hasMore | boolean | If the max count of actions per response has reached, this variable will be set to true |

JSON structure for each individual action in the array actions[]:

| Parameter | Type | Description |
| :---: | :---: | :--- |
| referenceId | String | referenceID for the message |
| actionType | String | Type of action being returned |
| actionBody | JSON object array specific to the actiontype | Array with objects specific to the actiontype |
| sender | String | Phone number of the user who sent the action to the group |
| sentAt | DateTime | Time when the action was posted to the group |

####  actionBody object structure for image/picture attachment:

| Parameter | Type | Description |
| :---: | :---: | :--- |
| imageURL | String | URL string for the picture |

##### Sample JSON Response:

```javascript
{
  "actions": [
    {
      "referenceId": "8a93c6cc-8499-44b0-aa54-016648100080",
      "actionType": "Image",
      "sender": "+9196500000",
      "creationTime": 1481180806,
      "actionBody": {
        "imageUrl": "https://kaizala.blob.core.windows.net/polymer/9540ca6cd6f0753314d6e.jpg"
      }
    }
]
}
```

####  actionBody object structure for the action 'Share Location':

| Parameter | Type | Description |
| :---: | :---: | :--- |
| latitude | Double | Latitude coordinates for the location |
| longitude | Double | Longitude coordinates for the location |

##### Sample JSON Response:

```javascript
{
  "actions": [
    {
      "referenceId": "3ba9f6b6-e968-44f2-a83a-acc03a3d18d3",
      "actionType": "ShareLocation",
      "sender": "+919900000",
      "creationTime": 1481180922,
      "actionBody": {
        "latitude": 17.429725,
        "longitude": 78.3408851
      }
    }
  ]
}
```

#### actionBody object structure for the action 'Photo with Location':

| Parameter | Type | Description |
| :---: | :---: | :--- |
| imageURL | String | URL string for the picture |
| latitude | Double | Latitude coordinates for the location |
| longitude | Double | Longitude coordinates for the location |

##### Sample JSON Response:

```javascript
{
  "actions": [
    {
      "referenceId": "3ba9f6b6-e968-44f2-a83a-acc03a3d18d3",
      "actionType": "ShareLocation",
      "sender": "+919900000",
      "creationTime": 1481180922,
      "actionBody": {
        "imageUrl": "https://kaizala.blob.core.windows.net/polymer/9540ca6cd6f0753314d6e.jpg",
        "latitude": 17.429725,
        "longitude": 78.3408851
      }
    }
  ]
}
```

####  actionBody object structure for the action 'Job':

| Parameter | Type | Description |
| :---: | :---: | :--- |
| actionId | String | GUID representing the specific action instance |
| title | String | Title of the Job |
| assigneeCount | Numeric | Number of assignees |
| responseCount | Numeric | Number of assignees who have marked the job complete |
| isCompleted | Boolean | True when all assignees have completed the job |

##### Sample JSON Response:

```javascript
{
  "actions": [
    {
      "referenceId": "3214841c-eaa2-4bf3-a583-acc69d9279c4",
      "actionType": "Job",
      "sender": "+919910005",
      "creationTime": 1481179788,
      "actionBody": {
        "actionId": "f260dc09-f1f3-4305-84f6-6edbedb82fb7",
        "title": "Test",
        "assigneeCount": 1,
        "responseCount": 0,
        "isCompleted": false
      }
    }
  ]
}
```
####  actionBody object structure for the action 'Poll':

| Parameter | Type | Description |
| :---: | :---: | :--- |
| actionId | String | GUID representing the specific action instance |
| question | String | Poll Question |
| isSenderOnly | Boolean | True when Poll Summary is visible only to sender |
| expiryDate | DateTime | DateTime of the Poll expiry time |
| Choices | Json Array | List of Json objects with following component <ol><li>title - Option Text</li><li>image - Option Image</li></ol> |

##### Sample JSON Response:

```javascript
{
    "actions": [
        {
            "referenceId": "d4753fdc-13fe-4162-a48f-5bf071bfd380",
            "actionType": "Poll",
            "sender": "+918585010248",
            "sentAt": "2017-12-20T08:33:51Z",
            "actionBody": {
                "actionId": "27c7dbcf-48bb-4523-8273-d53a3da2343b",
                "question": "Do you find Kaizala extensibility easy to use?",
                "isSenderOnly": false,
                "expiryDate": "2017-12-20T18:33:51Z",
                "choices": [
                    {
                        "title": "Yes",
                        "image": "https://cdn.kascore.osi.office.net/75e8e7b63d2a4c10cdc30208aa27f1c2987d868a0e764fc742a94f6549d8bdb2.png?sv=2015-12-11&sr=b&sig=4iqswjFVYyqGqyKg6cdMdUQmiAez8sV951UScUmLzLk%3D&st=2017-05-17T07%3A04%3A41Z&se=2291-03-02T08%3A04%3A41Z&sp=r"
                    },
                    {
                        "title": "No"
                    },
                    {
                        "title": "Not at all"
                    }
                ]
            }
        }
  ]
}
```
####  actionBody object structure for the action 'Let's Meet':

| Parameter | Type | Description |
| :---: | :---: | :--- |
| actionId | String | GUID representing the specific action instance |
| title | String | Title of the Meeting request |
| isSenderOnly | Boolean | True when Poll Summary is visible only to sender |
| duration | Integer | Duration of the meeting (in mins) |
| agenda | String | Agenda set for the meeting |
| startingTime | DateTime | DateTime of the Poll expiry time |
| Place | Json Object | Location Data with following component <ol><li>Latitude</li><li>Longitude</li><li>name</li></ol> |

##### Sample JSON Response:

```javascript
{
    "actions": [
        {
            "referenceId": "32d1e5ad-36ff-4237-a49c-4be95a10cd12",
            "actionType": "LetsMeet",
            "sender": "+918585010248",
            "sentAt": "2017-12-20T08:55:04Z",
            "actionBody": {
                "actionId": "3c80f0f1-2b2f-460a-b760-ec10adb7dbb1",
                "title": "lets catch up?",
                "startingTime": "2018-01-01T00:00:00Z",
                "agenda": "no agenda",
                "duration": 30,
                "isSenderOnly": false,
                "place": {
                    "latitude": 15,
                    "longitude": 96,
                    "name": "MS Building 3"
                }
            }
        }
  ]
}
```


####  actionBody object structure for the action 'Survey':

| Parameter | Type | Description |
| :---: | :---: | :--- |
| actionId | String | GUID representing the specific action instance |
| title | String | Title of the Survey |
| responseCount | Numeric | Number of people who responded to the Survey |
| expiryDate | DateTime | DateTime of the Survey expiry time |

##### Sample JSON Response:

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

Next: You can retrieve further details of each action instance with the corresponding actionId. [API for retrieving Action instance Details](actionDetails.md)
