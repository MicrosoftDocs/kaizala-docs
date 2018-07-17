---
title: /reaction
description: Reference Article for API to query reactions on any Action sent in a group
topic: Reference
author: nitinjms
---
# /reaction
API end-point to query reactions data on any Action sent in a group.

## POST /reaction

    POST {endpoint-url}/v1/groups/{groupId}/reaction

### Request Parameters

| | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---	| :--- |
| URL Path Parameter | groupId | String | No | GUID representing the groupId of the specific group resource |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |
| HTTP Header | Content-Type | String | No | value: application/json |

### Request body

| Parameter | Type | Optional? | Description |
| :---: | :---: | :--- | :--- |
| referenceId | String | No | GUID representing the id for entity reference representing an Action |
| sourceGroupId | String | No | GUID of the group in which the Action has been sent. In case of groups which is a subgroup of another group, this may differ from 'groupId' provided in the url Path parameter|
| reactionType | String | No | Enum value: 'Like'/'Comment'|
| comment | String | No | Comment text is mandatory only for reactionType 'Comment'. For 'Like', this should be ignored |

#### Sample JSON Request

```javascript
{
    "comment":"Comment-3",
    "referenceId":"4a44e62f-5142-a980-c7a48e2d92a8",
    "sourceGroupId":"fc6f2802-4431-b82f-60985a515b58",
    "reactionType":"Comment"
}
```

### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| reactionId | String | GUID representing the id for reaction entity after successful completion of the request |

#### Sample JSON Response

```javascript
{
    "reactionId": "71df-d53a-43cc-9b73-80dcc22502ab"
}
```
## GET /reaction summary at Action level

    GET {endpoint-url}/v1/groups/{groupId}/reaction/{referenceId}/summary?sourceGroupId={sourceGroupId}


## Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| URL Path Parameter | groupId | String | No | GUID representing the groupId of the specific group resource |
| URL Path Parameter | referenceId | String | No | GUID representing the id for entity reference representing an Action |
| URL Path Parameter | sourceGroupId | String | No | GUID of the group in which the Action has been sent |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |

## Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| summary | JSON Array | Array of JSON objects each representing reactions summary on a Action sent in a group |

### Response body summary object

| Parameter | Type | Description |
| :---: | :---: | :--- |
| referenceId | String | GUID representing the id for entity reference representing an Action |
| reactionsCountMap | Json object | Json object containing Likes and comments count for that referenceId |


### Sample JSON Response

```javascript
{
    "summary": [
        {
            "referenceId": "4a44e62e-4b42-a980-c7a48e2d92a8",
            "reactionsCountMap": {
                "like": 1,
                "comment": 4
            }
        }
    ]
}
```

## GET /reaction summary at group level

    GET {endpoint-url}/v1/groups/{groupId}/reaction/summary?sourceGroupId={sourceGroupId}&cursor={timeStamp}


### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| URL Path Parameter | groupId | String | No | GUID representing the groupId of the specific group resource |
| URL Path Parameter | sourceGroupId | String | No | GUID of the group in which the Action has been sent |
| URL Path Parameter | cursor | timeStamp | No | timeStamp from which the summary needs to be calculated. Default value 0 |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |

### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| cursor | timeStamp | timeStamp till which summary has been calculated. Next set of reactionSummary can be generated using this cursor value |
| summary | JSON Array | Array of JSON objects each representing reactions summary on a Action sent in a group |

#### Response body summary object

| Parameter | Type | Description |
| :---: | :---: | :--- |
| referenceId | String | GUID representing the id for entity reference representing an Action |
| reactionsCountMap | Json object | Json object containing Likes and comments count for that referenceId |


#### Sample JSON Response

```javascript
{
    "cursor": 636674054802000000,
    "summary": [
        {
            "referenceId": "4a44-51be-4b42-a980-c7a48e2d92a8",
            "reactionsCountMap": {
                "like": 1,
                "comment": 4
            }
        },
        {
            "referenceId": "4a44-51be-4b420-c7a48e2d92a8",
            "reactionsCountMap": {
                "like": 10,
                "comment": 14
            }
        }
    ]
}
```

## GET /reaction details for a Action

    GET {endpoint-url}/v1/groups/{groupId}/reaction/summary?sourceGroupId={sourceGroupId}&cursor={timeStamp}


### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| URL Path Parameter | groupId | String | No | GUID representing the groupId of the specific group resource |
| URL Path Parameter | sourceGroupId | String | No | GUID of the group in which the Action has been sent |
| URL Path Parameter | referenceId | String | No | GUID representing the id for entity reference representing an Action |
| URL Path Parameter | reactionType | String | No | Enum value: 'Like'/'Comment'|
| URL Path Parameter | cursor | TimeStamp | No | TimeStamp from which the summary needs to be calculated. Default value 0 |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |

### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| cursor | TimeStamp | TimeStamp till which reactionDetail has been provided. Next set of reactionDetails can be generated using this cursor value |
| reactionDetails | JSON Array | Array of JSON objects each representing reactions detail on an Action sent in a group |

#### Response body summary object

| Parameter | Type | Description |
| :---: | :---: | :--- |
| reactionId | String | GUID representing the id for reaction created on referenceId representing an Action |
| userId | Json object | UserId for the user who has created the reaction on an Action |
| lastModifiedTime | Timestamp | Timestamp at which reaction was created/updated |


#### Sample JSON Response

```javascript
{
    "cursor": 636674054802000000,
    "summary": [
        {
            "referenceId": "4a44-51be-4b42-a980-c7a48e2d92a8",
            "reactionsCountMap": {
                "like": 1,
                "comment": 4
            }
        },
        {
            "referenceId": "4a44-51be-4b420-c7a48e2d92a8",
            "reactionsCountMap": {
                "like": 10,
                "comment": 14
            }
        }
    ]
}
```