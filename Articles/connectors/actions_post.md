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


###### actionBody for an Announcement Action

| Parameter | Type | Optional? | Description |
| :---: | :---: | :---:	| :--- |
| title | String | No | Title of the Announcement |
| MediaResources | String[] | Yes | Array of media resources |
| Message | String | No | Message Body |

###### Sample JSON Request for an Announcement Action

```javascript
{
  "actionType" : "Announcement",
  "actionBody" : 
  {
    "Message":"Announcement from API Message text",
    "Title" : "Title text", 
    "MediaResources" : 
    [
      "eyJUaHVtYm5haWwiOiIvOWovNEFBUVNrWkpSZ0FCQVFFQVlBQmdBQUQvMndCREFJVmNaSFZrVTRWMWJIV1dqb1dleVAvWnlMZTN5UC8vLy9MLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8yd0JEQVk2V2xzaXZ5UC9aMmYvLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vL3dBQVJDQUNTQVFRREFTSUFBaEVCQXhFQi84UUFId0FBQVFVQkFRRUJBUUVBQUFBQUFBQUFBQUVDQXdRRkJnY0lDUW9MLzhRQXRSQUFBZ0VEQXdJRUF3VUZCQVFBQUFGOUFRSURBQVFSQlJJaE1VRUdFMUZoQnlKeEZES0JrYUVJSTBLeHdSVlMwZkFrTTJKeWdna0tGaGNZR1JvbEppY29LU28wTlRZM09EazZRMFJGUmtkSVNV","eyJUaHVtYm5haWwiOiIvOWovNEFBUVNrWkpSZ0FCQVFFQVlBQmdBQUQvMndCREFJVmNaSFZrVTRWMWJIV1dqb1dleVAvWnlMZTN5UC8vLy9MLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8yd0JEQVk2V2xzaXZ5UC9aMmYvLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vL3dBQVJDQUNTQVFRREFTSUFBaEVCQXhFQi84UUFId0FBQVFVQkFRRUJBUUVBQUFBQUFBQUFBQUVDQXdRRkJnY0lDUW9MLzhRQXRSQUFBZ0VE"
    ]
  }
}

```

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

###### actionBody for a Poll Action

| Parameter | Type | Optional? | Description |
| :---: | :---: | :---:	| :--- |
| question | String | No | Poll Question |
| Choices | Json Array | No | Choices available for the poll. Each Choice have below component: <ol><li>title (Mandatory & in String format) </li><li>image (optional)</li></ol> |
| expiryInHours | Integer | Yes | Default:720. Number of hours in which a gven poll would expire |

###### Sample JSON Request for a Poll Action

```javascript
{actionType:"Poll", actionBody:{question:"Do you find Kaizala extensibility easy to use?", 
	choices:
		[
		{title:"Yes",image:"eyJUaHVtYm5haWwiOiIvOWovNEFBUVNrWkpSZ0FCQVFFQVlBQmdBQUQvMndCREFJVmNaSFZrVTRWMWJIV1dqb1dleVAvWnlMZTN5UC8vLy9MLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8yd0JEQVk2V2xzaXZ5UC9aMmYvLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vLy8vL3dBQVJDQUNTQVFRREFTSUFBaEVCQXhFQi84UUFId0FBQVFVQkFRRUJBUUVBQUFBQUFBQUFBQUVDQXdRRkJnY0lDUW9MLzhRQXRSQUFBZ0VEQXdJRUF3VUZCQVFBQUFGOUFRSURBQVFSQlJJaE1VRUdFMUZoQnlKeEZES0JrYUVJSTBLeHdSVlMwZkFrTTJKeWdna0tGaGNZR1JvbEppY29LU28wTlRZM09EazZRMFJGUmtkSVNVcFRWRlZXVjFoWldtTmtaV1puYUdscWMzUjFkbmQ0ZVhxRGhJV0doNGlKaXBLVGxKV1dsNWlabXFLanBLV21wNmlwcXJLenRMVzJ0N2k1dXNMRHhNWEd4OGpKeXRMVDFOWFcxOWpaMnVIaTQrVGw1dWZvNmVyeDh2UDA5ZmIzK1BuNi84UUFId0VBQXdFQkFRRUJBUUVCQVFBQUFBQUFBQUVDQXdRRkJnY0lDUW9MLzhRQXRSRUFBZ0VDQkFRREJBY0ZCQVFBQVFKM0FBRUNBeEVFQlNFeEJoSkJVUWRoY1JNaU1vRUlGRUtSb2JIQkNTTXpVdkFWWW5MUkNoWWtOT0VsOFJjWUdSb21KeWdwS2pVMk56ZzVPa05FUlVaSFNFbEtVMVJWVmxkWVdWcGpaR1ZtWjJocGFuTjBkWFozZUhsNmdvT0VoWWFIaUltS2twT1VsWmFYbUptYW9xT2twYWFucUttcXNyTzB0YmEzdUxtNndzUEV4Y2JIeU1uSzB0UFUxZGJYMk5uYTR1UGs1ZWJuNk9ucTh2UDA5ZmIzK1BuNi85b0FEQU1CQUFJUkF4RUFQd0N4UlJSUUFVVVVVQUZGRkZBQlJSUlFBVVVVVUFGRkZGQUJSUlJRQVVVVVVBRkZGRkFCUlJSUUFVVVVVQUZGRkZBQlJSUlFBVVVVVUFGRkZGQUJSUlJRQVVVVVVBRkZGRkFCUlJSUUFVVVVsQUMwVW1hTTByZ0xSU1pvelJjQmFLVE5HYUxnTFJTWm96UmNCYUtUTkdhTGdMUlNab3pSY0JhS1ROR2FMb0JhS0tLWUJSUlJRQVVVVVVBRkZGRkFCUlJSUUFVVVVVQUZGRkZBQlJSUlFBVVVVVUFGSWVsTFNIcFNld0MwVVVVd0NpaWs3MEFMUlNZb3hTMUFXaWt4UmlqVUJhS1RGR0tOUUZvcE1VWW8xQVdrUFNqRkJIRkR2WUJhS1RGR0tOUUZvcE1VWW8xQVdpa3hSaWpVQmFLVEZHS05RRm9wQlMwd0NpaWlnQW9vb29BS0tLS0FDaWlpZ0FwRDBwYVE5S1QyQVdpaWltQVVuZWxwTzlJQmFLS0tZQlJSUlFBVVVVVUFGRkZGQUJTSHBTMGg2VW5zQXRGRkZNQW9vb29BS0tLS0FDaWlpZ0JPOUxTZDZXa2dDaWlpbUFVVVVVQUZGRkZBQlJSUlFBVVVVVUFKaWpGTFJTc2dFeFJpbHBPOUZrQVlveFMwVVdRQ1lveFMwVVdRQ1lveFMwVVdRQ1lveFMwVVdRQ1lveFMwVVdRQlJSUlRBS0tLS0FDaWlpZ0Fvb29vQVR2UzBuZWxwSUFvb29wZ0ZGRkZBQlJSUlFBVVVVVUFGRkZGQUJSUlJRQVVuZWxwTzlMc0F0RkZGTUFvb29vQUtLS0tBQ2lpaWdBb29vb0FLS0tLQUNpaWlnQW9vb29BS0tLS0FFNzB0SjNwYVNBS0tLS1lCUlJSUUFVVVVVQUZGRkZBQlJSUlFBVVVVVUFGSjNwYVR2U0FXaWlpbUFVVVVVQUZGRkZBQlJSUlFBVVVVVUFGRkZGQUJSUlJRQVVVVVVBRkZGRkFDZDZXazcwdEpBRkZGRk1Bb29vb0FLS0tLQUNpaWlnQW9vb29BS0tLS0FDa3BhS0FFeFJpbG9wV1FDWW94UzBVV1FDWW94UzBVV1FDWW94UzBVV1FDWW94UzBVV1FDWW94UzBVV1FDWW94UzBVV1FDWW94UzBVV1FDWW94UzBVV1FDVXRGRk1Bb29vb0FLS0tLQUNpaWlnQW9vb29BS0tLS0FDaWlpZ0Fvb29vQUtLS0tBQ2lpaWdBb29vb0FLS0tLQUNpaWlnQW9vb29BS0tLS0FDaWlpZ0Fvb29vQUtLS0tBQ2lpaWdBb29vb0FLS0tLQUNpaWlnQW9vb29BS0tLS0FDaWlpZ0Fvb29vQUtLS0tBQ2lpaWdBb29vb0FLS0tLQUNpaWlnQW9vb29BS0tLS0FDaWlpZ0Fvb29vQUtLS0tBQ2lpaWdELzlrPSIsIkFjdGlvblR5cGUiOjMsIkZpbGVzIjpbeyJJZCI6ImU1Y2YyMWJmLWQ3OGItNGY4Yi1iYjY3LTM2NTJlNDk1ZDEyZSIsIk5hbWUiOiJ0ZXN0LnBuZyIsIlNpemUiOjQsIlVybCI6Imh0dHBzOi8vY2RuLmthc2NvcmUub3NpLm9mZmljZS5uZXQvNzVlOGU3YjYzZDJhNGMxMGNkYzMwMjA4YWEyN2YxYzI5ODdkODY4YTBlNzY0ZmM3NDJhOTRmNjU0OWQ4YmRiMi5wbmc/c3Y9MjAxNS0xMi0xMSZzcj1iJnNpZz00aXFzd2pGVll5cUdxeUtnNmNkTWRVUW1pQWV6OHNWOTUxVVNjVW1MekxrJTNEJnN0PTIwMTctMDUtMTdUMDclM0EwNCUzQTQxWiZzZT0yMjkxLTAzLTAyVDA4JTNBMDQlM0E0MVomc3A9ciJ9XX0="},
		{title:"No"},
		{title:"Not at all"}
		],
	expiryInHours:10}}
```
###### actionBody for a Let's Meet Action

| Parameter | Type | Optional? | Description |
| :---: | :---: | :---:	| :--- |
| title | String | No | Title of the Meeting Request  |
| startingTime | DateTime | No | Starting time for the meeting |
| DurationInMins | Integer | No | Default: 30 mins. Number of minutes for which a meeting would be conducted |
| place | JSON object | Yes | Meeting Location. Contains 3 components: latitude, longitude, name  |
| agenda | String | Yes | Agenda for the Meeting / Description for the meeting |
| isSenderOnly | Bool | Yes | For allowing only sender to view Let's Meet summary. Default: false |

###### Sample JSON Request for a Let's Meet Action

```javascript
{actionType:"LetsMeet", actionBody:{title:"lets catch up?", startingTime:"2018-01-01T00:00:00Z", duration:45, place:{"latitude":15.0,"longitude":96.0,"name":"MS Building 3"}, agenda:"no agenda", isSenderOnly:false}}

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
