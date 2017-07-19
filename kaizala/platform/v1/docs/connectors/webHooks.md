## /webhook
API end-point to manage subscriptions to events inside Kaizala.

WebHooks is a lightweight HTTP pattern providing a simple publisher/subscriber model for wiring together Web APIs and SaaS services. When an event happens in Kaizala, a notification is sent in the form of an HTTP POST request to registered subscribers. The POST request contains information about the event which makes it possible for the receiver to act accordingly.

Using WebHooks, you can subscribe to various events that occur within a conversation group context in Kaizala.

### POST /webhook

    POST https://{api_root}/webhook

##### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| HTTP Header | applicationId | String | No | ID associated with the Connector that was registered by the developer – on behalf of which the API calls need to be made |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |

##### Request body

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| objectId | String | No | GUID representing the group in which context the webhooks need to be created |
| ObjectType | String | No | Only supported type currently is "Group" |
| eventTypes | Array | No | Array of different types of events you need to subscribe the webhook to. Supported events are: ActionCreated, ActionResponse, SurveyCreated, JobCreated, SurveyResponse, JobResponse |
| callBackUrl | String | No | HTTPS URL to which the subscribed events need to be notified to |
| callBackToken | String | Yes | Optional parameter you can set which will be sent in the HTTP header 'kz-callback-token' with every callBack made by the WebHook |
| callBackContext | String | Yes | Optional parameter you can set which will be sent in the JSON payload as 'context' with every callBack made by the WebHook |
| validity | String | Yes | Validity for the WebHook to be active in EPOCH format. Default is 2 years |

##### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| webhookId | String | GUID representing the webHook created |
