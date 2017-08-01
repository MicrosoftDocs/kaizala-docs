### POST /actions

    POST https://{api_root}/groups/{groupId}/actions

##### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| URL Path Parameter | groupId | String | No | GUID representing the groupId of the specific group resource |
| HTTP Header | applicationId | String | No | ID associated with the Connector that was registered by the developer – on behalf of which the API calls need to be made |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |
| HTTP Header | Content-Type | String | No | value: application/json |

##### Request body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| id | String | Id of the Kaizala Action to send. Please refer to the table above for supported Actions and their respective IDs. |
| actionBody | JSON Object | Object representing data needed for the respective Action. Parameters defined below for each of the supported Actions. |

###### actionBody for a Job Action

| Parameter | Type | Optional? | Description |
| :---: | :---: | :---:	| :--- |
| title | String | No | Title for the job |
| assignedTo | String Array | No | Array of well formatted phone numbers to whom the job needs to be assigned |
| dueDate | Numeric | Yes | Time to complete the job in Hours (Default: 24hrs) |

####### Sample JSON Request for a Job Action

```javascript
{
    actionType:"Job",
    actionBody: {
        title:"Sample job request",
        assignedTo:[
            "+91900000000"],
        dueDate:10}
        }
}
```

###### actionBody for a Survey Action:

| Parameter | Type | Optional? | Description |
| :---: | :---: | :---:	| :--- |
| title | String | No | Title for the survey |
| questions | JSON Object Array | No | Array of questions for the survey. Format for the json object is given below. |
| isAnonymous | Boolean | Yes | If set to true, the responses will be anonymous. |
| dueDate | Numeric | Yes | Time in which the survey closes in Hours (Default: 24hrs) |

####### Structure for questions[] inside a survey

| Parameter | Type | Optional? | Description |
| :---: | :---: | :---:	| :--- |
| title | String | No | Question Title |
| type | String | No | Has to be one of TEXT MULTIOPTION SINGLEOPTION NUMERIC IMAGE |
| options | JSON Object Array | Yes | Options for selection type questions in an array format. Array containing strings of name “title” with the option values. |

####### Sample JSON Request for a Survey Action

```javascript
{
    actionType:"Survey",
    actionBody: {
        title:"Sample survey",
        questions:[
                {title:"Provide a name for this response",
                type:"Text"},
                {title:"Test multiple",
                type:"MultiOption",
                options:[
                    {title:"Yes"},
                    {title:"No"},
                    {title:"Maybe"}
                    ]},
                {title:"Test number",
                type:"Numeric"},
                {title:"Test",
                type:"Image"}
                ]
            }
}
```

###### actionBody for a Media(Image/Album/Audio/Document) attachment

| Parameter | Type | Optional? | Description |
| :---: | :---: | :---:	| :--- |
| mediaResource | String | No | MediaResource string from a previous call to /media where you need to upload the attachment  |
| caption | String | Yes | Caption that will appear on Kaizala client alongwith media  |

####### Sample JSON Request for a Media Action

```javascript
{
    actionType:"Image",
    actionBody: {
                mediaResource: "{{MediaResource return in response of /media api call}}",
                caption: "Sample test caption"
                }
}

```

###### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| referenceId | String | GUID representing the succesful completion of the request |
| actionId | String | GUID representing the specific instance of the Action that was sent. This can be used later to retrieve information about this specific Action instance. |

```javascript
{
    "referenceId": "853654b2-5874-462d-b709-0c4e43a7083f",
    "actionId": "e478e860-8cb5-4660-999d-6435aaee8c87"
}
```
