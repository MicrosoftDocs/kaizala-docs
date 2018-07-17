---
title: /subscribers
description: Reference Article for API to get subscribers data for public groups
topic: Reference
author: nitinjms
---
# /subscribers

API end-point to add, get or delete subscribers from Managed Public group.

## ADD /subscribers

    PUT {endpoint-url}/v1/groups/{groupId}/subscribers/add

### Request Parameters
|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---: | :--- |
| URL Path Parameter | groupId | String | No | GUID representing the groupId of the specific group resource |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |

### Request body
| Parameter | Type | Description |
| :---: | :---: | :--- |
| subscribers | String[] | Each string represents mobile number with country code(Eg. +911111111111) |

#### Sample JSON Request
```javascript
{
    subscribers : ["+911111111111", "+911111111112"]
}
```

### Response body
| Parameter | Type | Description |
| :---: | :---: | :--- |
| result | JSON object | each key of this Json Object represents the mobile number and value represents the Json object containing success or failure with reason |

#### Sample JSON Response

```javascript
{
    "result": {
        "+911111111111": {
            "isAdded": true
        },
        "+911111111112": {
            "isAdded": true
        }
    }
}
```

## GET /subscribers

    POST {endpoint-url}/v1/groups/{groupId}/subscribers

### Request Parameters
|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---: | :--- |
| URL Path Parameter | groupId | String | No | GUID representing the groupId of the specific group resource |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |

### Request body

| Parameter | Type | Optional? | Description |
| :---: | :---: | :--- | :--- |
| cursor | String | Yes | Start of resultset. For pagination. Returned in Response Body |
| count | int | Yes | Default: 50. Max: 50. Number of subscribers to be returned in a resultset|

### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| subscribers | JSON Array | Array of JSON objects each representing a subscriber of the group |
| cursor | String | Start of resultset. For pagination. To be used in Request body for fetching next result set. Present in response only if there is a valid next result set. |

#### Sample JSON Response

```javascript
{
    "subscribers": [
        {
            "id": "e2238eb5-2f45-4783-8f4b-571549db86c0",
            "mobileNumber": "+91109999999",
            "name": "",
            "profilePic": "",
            "isProvisioned": false
        }
    ]
}
```

## REMOVE /subscribers

    PUT {endpoint-url}/v1/groups/{groupId}/subscribers/remove

### Request Parameters
|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---: | :--- |
| URL Path Parameter | groupId | String | No | GUID representing the groupId of the specific group resource |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |

### Request body
| Parameter | Type | Description |
| :---: | :---: | :--- |
| subscribers | String[] | Each string represents mobile number with country code(Eg. +911111111111) |

#### Sample JSON Request
```javascript
{
    subscribers : ["+911111111111", "+911111111112"]
}
```

### Response body
| Parameter | Type | Description |
| :---: | :---: | :--- |
| result | JSON object | each key of this Json Object represents the mobile number and value represents the Json object containing success or failure with reason |

#### Sample JSON Response

```javascript
{
    "result": {
        "+911111111111": {
            "isRemoved": true
        },
        "+911111111112": {
            "isRemoved": true
        }
    }
}
```

