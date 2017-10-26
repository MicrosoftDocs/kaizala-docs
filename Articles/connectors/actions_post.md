---
title: /Actions_post
description: Reference Article for API to post action on a Kaizala group
topic: Reference
author: nitinjms
---
# Post a Action in a group
### POST /actions

    POST {endpoint-url}/groups/{groupId}/actions

##### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| URL Path Parameter | groupId | String | No | Group Identifier |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |
| HTTP Header | Content-Type | String | No | value: application/json |

##### Request body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| id | String | Id of the Kaizala Action package. Either of actionType or Id should be specified |
| actionType | String | Enum "Survey"/"Job". Either of actionType or Id should be specified |
| actionBody | JSON Object | Object representing data needed for the respective Action. Parameters defined below for each of the supported Actions. |

###### actionBody for a Job Action

| Parameter | Type | Optional? | Description |
| :---: | :---: | :---:	| :--- |
| title | String | No | Title of the Job |
| assignedTo | String[] | No | Title of the Job |
| dueDate | long | Yes | Default: 24hrs. Number of hours before which job should be completed |

###### Sample JSON Request for a Job Action

```javascript
{
    actionType:"Job",
    actionBody: {
        title : "test job",
        assignedTo : ["+911111111111", "+911111111112"],
        dueDate : 10
    }
}

```

###### actionBody for a Survey Action Or Action package instance(id) :

| Parameter | Type | Optional? | Description |
| :---: | :---: | :---:	| :--- |
| title | String | No | Title of the Job |
| dueDate | long | Yes | Default: 24hrs. Number of hours before which job should be completed |
| isAnonymous | Bool | Yes | For allowing anonymous survey responses. Default: false |
| isSenderOnly | Bool | Yes | For allowing only sender to view survey summary. Default: false |
| acceptMultipleResponses | Bool | Yes | For allowing multiple responses from same responder. Default: false |
| questions | object[] | No | Each element of object[] is described below as Question object |
| properties | object[] | No | Each element of object[] is described below as Property Object. Only valid for creating Action Package Instance |

###### Structure for Question object

| Parameter | Type | Optional? | Description |
| :---: | :---: | :---:	| :--- |
| title | String | No | Title of the question |
| type | String | No | Type of the question. Enum: SingleOption/MultiOption/Text/Image/Numeric/Date/Location/AttachmentList |
| isInvisible | Bool | Yes | Default: false. To control the visibility of the question |
| options | object[] | Yes | Mandatory for SingleOption and MultiOption question type. each element of object[] is described below as Option object |

###### Structure for Option object

| Parameter | Type | Optional? | Description |
| :---: | :---: | :---:	| :--- |
| title | String | No | Title of the Option |

###### Structure for Property object

| Parameter | Type | Optional? | Description |
| :---: | :---: | :---:	| :--- |
| name | String | No | Name of the property |
| type | String | No | Type of the property. Enum: Text, Numeric, Location, DateTime, StringList, Attachment, StringSet, AttachmentList |
| value | String | No | Value of the property |

###### Sample JSON Request for a Survey Action

```javascript
{
  actionType: "Survey",
  actionBody: {
    isAnonymous:false,
    isSenderOnly:false,
    acceptMultipleResponses:true,
    dueDate:10,
    title: "A test survey!!",
    questions: [
    	{
    		title: "a test question written here",
    		type: "Text"
    	},
    	{
    		title: "Single select question",
    		type: "SingleOption",
    		options: [{title:"Opt1"},{title:"Opt2"}]
    	},
    	{
    		title: "Multi select question",
    		type: "MultiOption",
    		options: [{title:"MOpt1"},{title:"MOpt2"},{title:"MOpt3"}]
    	},
    	{
    		title: "Numeric question",
    		type: "Numeric"
    	},
    	{
    		title: "Location question",
    		type: "Location"
    	},
    	{
    		title: "DateTime question",
    		type: "DateTime"
    	},
    	{
    		title: "Image question",
    		type: "Image"
    	}
    	]
  }
}
```

###### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| referenceId | String | Request identifier |
| actionId | String | Action identifier |

```javascript
{
    "referenceId": "79f43f77-d586-4e9a-b8b8-103e0ac5b782",
    "actionId": "232e7003-22a1-4a28-bb36-9176e704e10c"
}
```
