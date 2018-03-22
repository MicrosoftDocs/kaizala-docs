---
title: /webhooks
description: Reference Article for API to manage Kaizala subscriptions
topic: Reference
author: nitinjms
---
# APIs to register & manage webhooks
## /webhook
API end-point to manage subscriptions to events inside Kaizala.

WebHooks is a lightweight HTTP pattern providing a simple publisher/subscriber model for wiring together Web APIs and SaaS services. When an event happens in Kaizala, a notification is sent in the form of an HTTP POST request to registered subscribers. The POST request contains information about the event which makes it possible for the receiver to act accordingly.


Using WebHooks, you can subscribe to various events that occur within a conversation group context in Kaizala.

### POST /webhook

    POST {endpoint-url}/v1/webhook

##### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point || HTTP Header | Content-Type | String | No | "application/json" |

##### Request body

|  Parameter | Type | Optional? | Description |
| :---: | :---: | :---:	| :--- |
| objectId | String | No | Identifier representing the object in which context the webhooks need to be created.For ObjectType=Group, its group's Identifier, For ObjectType=Action, its actionId, For ObjectType=ActionPackage, its action-package-id |
| objectType | String | No | Enum: "Group"/"Action"/"ActionPackage" |
| eventTypes | Array | No | Array of different types of events you need to subscribe the webhook to. Supported events are: "ActionCreated","ActionResponse","SurveyCreated","JobCreated","SurveyResponse","JobResponse","TextMessageCreated","AttachmentCreated","Announcement","MemberAdded","MemberRemoved","GroupAdded","GroupRemoved" |
| callBackUrl | String | No | HTTPS URL to which the subscribed events need to be notified to |
| callBackToken | String | Yes | Optional parameter you can set which will be sent in the HTTP header 'kz-callback-token' with every callBack made by the WebHook |
| callBackContext | String | Yes | Optional parameter you can set which will be sent in the JSON payload as 'context' with every callBack made by the WebHook |
| validity | String | Yes | Validity for the WebHook to be active in EPOCH format. Default is 2 years |

##### Response body
| Parameter | Type | Description |
| :---: | :---: | :--- |
| webhookId | String | Identifier representing the webHook created |

##### Request Body - Subscribe to all events at group level

```javascript
{  
   "objectId":"74943849802190eaea3810",
   "objectType":"Group",
   "eventTypes":[
      "ActionCreated",
      "ActionResponse",
      "SurveyCreated",
      "JobCreated",
      "SurveyResponse",
      "JobResponse",
      "TextMessageCreated",
      "AttachmentCreated",
      "Announcement",
      "MemberAdded",
      "MemberRemoved",
      "GroupAdded",
      "GroupRemoved"
   ],
   "callBackUrl":"https://requestb.in/123",
   "callBackToken":"tokenToBeVerifiedByCallback",
   "callBackContext":"Any data which is required to be returned in callback"
}

```


### Get /webhook

    GET {endpoint-url}/v1/webhook

##### Request Parameters


|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---: | :--- |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |
| Query parameter | objectId | String | No | Identifier representing the object in which context the webhooks need to be created.For ObjectType=Group, its group's Identifier, For ObjectType=Action, its actionId, For ObjectType=ActionPackage, its action-package-id |
| Query parameter | objectType | String | No | Enum: "Group"/"Action"/"ActionPackage" |

##### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| webhooks | JSON Object Array | Array of webhooks subscribed on the objectId |

######  JSON structure for each individual webhook in the array webhooks[]:

| Parameter | Type | Description |
| :---: | :---: | :--- |
| id | String | Webhook Identifier |
| objectId | String | Object Identifier |
| objectType | String | Enum: "Group"/"Action"/"ActionPackage" |
| events | String[] | Event list with each value as one of "ActionCreated","ActionResponse","SurveyCreated","JobCreated","SurveyResponse","JobResponse","TextMessageCreated","AttachmentCreated","Announcement","MemberAdded","MemberRemoved","GroupAdded","GroupRemoved" |
| callBackUrl | String | Callback URL to which the subscribed events need to be notified to |
| callBackToken | String | Parameter which will be sent in the HTTP header 'kz-callback-token' with every callBack made by the WebHook |
| callBackContext | String | Parameter sent in the JSON payload as 'context' with every callBack made by the WebHook |
| validity | String | Validity for the WebHook to be active in EPOCH format. |

###### Sample JSON Response

```javascript
{
    "webhooks": [
        {
            "id": "dac6fccf-f2e9-4abc-94d7-793037e99da7",
            "objectId": "b21405d1-4b10-4c46-bfa9-8338592f3782",
            "objectType": "Group",
            "events": [
                "ActionCreated",
                "ActionResponse",
                "SurveyCreated",
                "JobCreated",
                "SurveyResponse",
                "JobResponse",
                "TextMessageCreated",
                "AttachmentCreated",
                "Announcement",
                "MemberAdded",
                "MemberRemoved",
                "GroupAdded",
                "GroupRemoved"
            ],
            "filters": [],
            "callbackUrl": "https://requestb.in/12786un1",
            "callbackToken": "tokenToBeVerifiedByCallback",
            "ts": 1505491564677,
            "validity": 1568605416677
        }
    ]
}
```

### Delete /webhook

    DELETE {endpoint-url}/v1/webhook

##### Request Parameters
|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---: | :--- |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |
| Path parameter | webhookId | String | No | Webhook Identifier |
