---
title: /messages
description: Reference Article for API to query messages sent ina group
topic: Reference
author: nitinjms
---
# APIs to query messages sent in a group
## /messages
API end-point to send messages to conversation groups inside Kaizala.

### POST /messages

    POST {endpoint-url}/v1/groups/{groupId}/messages

##### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| URL Path Parameter | groupId | String | No | GUID representing the groupId of the specific group resource |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |
| HTTP Header | Content-Type | String | No | value: application/json |

##### Request body

| Parameter | Type | Optional? | Description |
| :---: | :---: | :--- | :--- |
| message | String | No | Text message to be sent (Max limit of 1000 Characters) |
| sendToAllSubscribers | Bool | Yes | Default: false. Valid only in case the groupId belongs to a Public Group. True to send the text message to all subscribers which requires the token's user to be admin of the Public Group |
| subscribers | String[] | Yes | Each element corresponds to a mobile number(with country code. Eg. +911999999999). Text message will be sent only to the selected subscribers. To be used for selective communication to subscribers in context of a Public Group |

###### Sample JSON Request

```javascript
{
  "message": "Hello All! Welcome to Kaizala.",
  "subscribers": ["+911999999999","+911999999998"]
}
```

##### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| referenceId | String | GUID representing the succesful completion of the request |

###### Sample JSON Response

```javascript
{
    "referenceId": "853654b2-5874-462d-b709-0c4e43a7083f"
}
```
