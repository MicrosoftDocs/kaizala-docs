# Webhook response schema for registered events

If a webhook is registered, Kaizala returns a webHook response for each event on the registered objectId, filtered for registered events. 
Below is schema details for different webhook response for different events.

## Response Body
| Parameter | Type | Description |
| :---: | :---: | :--- |
| objectId | String | Identifier representing the object in which context the webhook has been created.For ObjectType=Group, its group's Identifier, For ObjectType=Action, its actionId, For ObjectType=ActionPackage, its action-package-id |
| objectType | String | Enum: "Group"/"Action"/"ActionPackage" |
| eventType | String | Registered event that has been invoked |
| eventId | String | Identifier representing the event |
| data | JSON Object | Object representing data specific to that event. Parameters defined below for each of the supported event. |
| context | String | Returns value that has been set while registering a webhook under parameter 'callbackContext'|
| fromUser | String | Sender's phone number |
| fromUserId | String | Sender's userId |
| fromUserName | String | Sender's registered name with Kaizala |
| fromUserProfilePic | url | Sender's Profile Pic |

The parameter 'data' would vary depending on the webHook event. You can find schema for each event below.

### data for event 'TextMessageCreated'
| Parameter | Type | Description |
| :---: | :---: | :--- |
| text | String | Text Message that has been sent |

#### Sample webHook response for 'TextMessageCreated'
```javascript
{
  "objectId": "8c2050-9be8-45d6-97f5-bb7013930027",
  "objectType": "Group",
  "eventType": "TextMessageCreated",
  "eventId": "55ed01-02b5-491e-8e7e-484726da976b",
  "data": {
    "text": "Test Message"
  },
  "context": "Any data which is required to be returned in callback",
  "fromUser": "+91xxxxxxxx",
  "fromUserId": "72e91-f3-4e7b-84eb-4e228406fb9b",
  "fromUserName": "Robin Richard",
  "fromUserProfilePic": "https://mobileonlyapps.blob.core.windows.net/72e29591-4e7b-84eb-4e228406fb9b/c34afc0d53614ae29285d08e6409e416.jpg"
}
```

### data for event 'AttachmentCreated'
| Parameter | Type | Description |
| :---: | :---: | :--- |
| media | Array | Each item contains mediaUrl and mediaFileName|
| mediaUrl | url | url of the image |
| mediaFileName | String | Filename |
| actionType | String | Enum value : 'Image' |
| caption | String | caption attached with the image |

#### Sample webHook response for 'AttachmentCreated'
```javascript
{
  "objectId": "8c291050-9be8-45d6-97f5-bb7013930027",
  "objectType": "Group",
  "eventType": "AttachmentCreated",
  "eventId": "59e2e9f9-9b10-4b67-8bc5-3f85a04f2d91",
  "data": {
    "media": [
      {
        "mediaUrl": "https://cdn.inc-000.kms.osi.office.net/att/0ad142c52b30d797addebadb620c19bf6f018299ed4acdce5760e45e2e4bc4ae.jpg?sv=2015-12-11&amp;sr=b&amp;sig=Thbp46wdgoqbDaAF06v2Y2ijzny0jx2fBDo1EZab%2BNY%3D&amp;st=2018-03-22T10:22:21Z&amp;se=2292-01-05T11:22:21Z&amp;sp=r",
        "mediaFileName": "IMG_18-03-22_165220084_1.jpg"
      }
    ],
    "actionType": "Image",
    "caption": "Testing."
  },
 "context": "Any data which is required to be returned in callback",
  "fromUser": "+91xxxxxxxx",
  "fromUserId": "72e91-f3-4e7b-84eb-4e228406fb9b",
  "fromUserName": "Robin Richard",
  "fromUserProfilePic": "https://mobileonlyapps.blob.core.windows.net/72e29591-4e7b-84eb-4e228406fb9b/c34afc0d53614ae29285d08e6409e416.jpg"
}
```
### data for event 'Announcement'
| Parameter | Type | Description |
| :---: | :---: | :--- |
| title | String | Title of Announcement Action |
| text | String | Message body of Announcement Action |
| media | Array | Each item contains mediaUrl and mediaFileName|
| mediaUrl | url | url of the image |
| mediaFileName | String | Filename |


#### Sample webHook response for 'Announcement'
```javascript
{
  "objectId": "8c291050-9be8-45d6-97f5-bb7013930027",
  "objectType": "Group",
  "eventType": "Announcement",
  "eventId": "3e49b367-acf6-48a7-a675-6bf4d372a070",
  "data": {
    "text": "Caption :Testing.",
    "title": "Sent by Robin Richard",
    "media": [
      {
        "url": "https://cdn.inc-000.kms.osi.office.net/contenthost/beb2cfef8732c6cc3b54652c1f6f99d64f529fd9be3d409e2966552639fb791f.jpeg",
        "fileName": "e3c145f1-5e6f-4ee9-bd83-49ec3a1c2550.jpeg"
      }
    ]
  },
 "context": "Any data which is required to be returned in callback",
  "fromUser": "+91xxxxxxxx",
  "fromUserId": "72e91-f3-4e7b-84eb-4e228406fb9b",
  "fromUserName": "Robin Richard",
  "fromUserProfilePic": "https://mobileonlyapps.blob.core.windows.net/72e29591-4e7b-84eb-4e228406fb9b/c34afc0d53614ae29285d08e6409e416.jpg"
}
```

### data for event 'JobCreated'
| Parameter | Type | Description |
| :---: | :---: | :--- |
| title | String | Title of Announcement Action |
| text | String | Message body of Announcement Action |
| actionId | Id | Identifier for that particular instance of Job Action |
| dueDate | Date | Date by which job would expire |
| assignedTo | String Array | Array of phone numbers |


#### Sample webHook response for 'JobCreated'
```javascript
{
  "objectId": "8c2950-9be8-45d6-97f5-bb7013930027",
  "objectType": "Group",
  "eventType": "JobCreated",
  "eventId": "3e49b367-acf6-48a7-a675-6bf4d372a070",
  "data": {
    "assignedTo": [
      "+919740797266"
    ],
    "title": "Test Job",
    "dueDate": "2018-03-22T18:29:59Z",
    "actionId": "aeb012-31a0-477a-a131-8a1e2791b36e",
    "groupId": "8c291050-9be8-6-97f5-bb7013930027"
  },
 "context": "Any data which is required to be returned in callback",
  "fromUser": "+91xxxxxxxx",
  "fromUserId": "72e91-f3-4e7b-84eb-4e228406fb9b",
  "fromUserName": "Robin Richard",
  "fromUserProfilePic": "https://mobileonlyapps.blob.core.windows.net/72e29591-4e7b-84eb-4e228406fb9b/c34afc0d53614ae29285d08e6409e416.jpg"
}
```

### data for event 'JobResponse'
| Parameter | Type | Description |
| :---: | :---: | :--- |
| title | String | Title of Announcement Action |
| text | String | Message body of Announcement Action |
| actionId | Id | Identifier for that particular instance of Job Action |
| groupId | String | Group Identifier |
| responseId | String | GUID for identifying that Response |
| responseDetails | String Array | Array of Response Objects |
| assignee | String | Assignee's Phone Number |
| assigneeName | String | Assignee's Name |
| assigneeProfilePic | url | url of the assignee's profile pic |
| isCompleted | Boolean | Is the Job completed? |




#### Sample webHook response for 'JobResponse'
```javascript
{
  "objectId": "8c2950-9be8-45d6-97f5-bb7013930027",
  "objectType": "Group",
  "eventType": "JobResponse",
  "eventId": "3e49b367-acf6-48a7-a675-6bf4d372a070",
  "data": {
    "actionId": "2ce34820-3d67-4807-9a1d-7cf099c2e7ae",
    "groupId": "8c291050-9be8-45d6-97f5-bb7013930027",
    "responseId": "80a883ec-e6c7-4dc8-979d-d268bbeeee8b",
    "responseDetails": {
      "response": {
        "assignee": "++91xxxxxxxx",
        "assigneeName": "Robin Richard",
        "assigneeProfilePic": "https://mobileonlyapps.blob.core.windows.net/72e29591-f391-4e7b-84eb-4e228406fb9b/c34afc0d536285d08e6409e416.jpg",
        "isCompleted": true
      }
    }
  },
  "context": "Any data which is required to be returned in callback",
  "fromUser": "+91xxxxxxxx",
  "fromUserId": "72e91-f3-4e7b-84eb-4e228406fb9b",
  "fromUserName": "Robin Richard",
  "fromUserProfilePic": "https://mobileonlyapps.blob.core.windows.net/72e29591-4e7b-84eb-4e228406fb9b/c34afc0d53614ae29285d08e6409e416.jpg"
}
```

### data for event 'ActionCreated' / 'SurveyCreated'
| Parameter | Type | Description |
| :---: | :---: | :--- |
| actionId | Id | Identifier for that particular instance of Job Action |
| groupId | String | Group Identifier |
| responseId | String | GUID for identifying that Response |
| questions | String Array | Array of Objects |
| responder | String | responder's Phone Number |
| responderName | String | responder's Name |
| responderProfilePic | url | url of the responder's profile pic |
| isAnonymous | Boolean | Is the Survey response been submitted anonymously |
| isUpdateResponse | Boolean | Has the response been updated by responder, since the response was submitted earlier |


#### Schema details for 'responseWithQuestions' object
| Parameter | Type | Description |
| :---: | :---: | :--- |
| title | String | Question Title |
| type | String | QuestionType |
| options | Array | List of options (key-value pair) applicable for Multi-choice questions |
| isInvisible | Boolean | Is the question hidden from UI |



#### Sample webHook response for 'ActionCreated' / 'SurveyCreated'
```javascript
{
  "objectId": "8c2950-9be8-45d6-97f5-bb7013930027",
  "objectType": "Group",
  "eventType": "ActionCreated",
  "eventId": "3e49b367-acf6-48a7-a675-6bf4d372a070",
  "data": {
   "actionId": "920f9802-62dafb-9bc2-8d3ba5c43609",
    "groupId": "8c291050-9be8-4d6-97f5-bb7013930027",
    "responseId": "420e9ef0-2a6d-405-a2bf-2688648ce79a",
    "isUpdateResponse": false,
    "responder": "+91xxxxxxxxx",
    "responderName": "Robin Richard",
    "responderProfilePic": "https://mobileonlyapps.blob.core.windows.net/72e29591-f391-4e7b-84eb-4e228406fb9b/c34afc0d53614ae29285d08e6409e416.jpg",
    "isAnonymous": false,
    "responseDetails": {
      "responseWithQuestions": [
        {
          "title": "1",
          "type": "Text",
          "options": [],
          "answer": "1"
        },
        {
          "title": "2",
          "type": "AttachmentList",
          "options": [],
          "answer": [
            {
              "mediaUrl": "https://cdn.inc-000.kms.osi.office.net/att/9841be297131449fba1123ec8545ab30fa72c2017555ba4bcd4ac18d5f7850b4.jpg?sv=2015-12-11&amp;sr=b&amp;sig=Egd4wDmAfGrIoklLj70SrV7D3QtwtMEWQx673U%3D&amp;st=2018-03-23T09:26:24Z&amp;se=2292-01-06T10:26:24Z&amp;sp=r",
              "mediaFileName": "IMG_18-03-23_155619990_1.jpg"
            }
          ]
        },
        {
          "isInvisible": true,
          "title": "ResponseTime",
          "type": "DateTime",
          "options": [],
          "answer": 1521800782956
        }
      ]
    }
  },
  "context": "Any data which is required to be returned in callback",
  "fromUser": "+91xxxxxxxx",
  "fromUserId": "72e91-f3-4e7b-84eb-4e228406fb9b",
  "fromUserName": "Robin Richard",
  "fromUserProfilePic": "https://mobileonlyapps.blob.core.windows.net/72e29591-4e7b-84eb-4e228406fb9b/c34afc0d53614ae29285d08e6409e416.jpg"
}
```



### data for event 'SurveyResponse'/ 'ActionResponse'
| Parameter | Type | Description |
| :---: | :---: | :--- |
| actionId | Id | Identifier for that particular instance of Job Action |
| groupId | String | Group Identifier |
| responseId | String | GUID for identifying that Response |
| responseDetails | String Array | Array of 'responseWithQuestions' Objects |
| responder | String | responder's Phone Number |
| responderName | String | responder's Name |
| responderProfilePic | url | url of the responder's profile pic |
| isAnonymous | Boolean | Is the Survey response been submitted anonymously |
| isUpdateResponse | Boolean | Has the response been updated by responder, since the response was submitted earlier |


#### Schema details for 'responseWithQuestions' object
| Parameter | Type | Description |
| :---: | :---: | :--- |
| title | String | Question Title |
| type | String | QuestionType |
| options | Array | List of options applicable for Multi-choice questions |
| answer | Array of Json Object | Answers |
| isInvisible | Boolean | Is the question hidden from UI |



#### Sample webHook response for 'SurveyResponse' 'ActionResponse'
```javascript
{
  "objectId": "8c2950-9be8-45d6-97f5-bb7013930027",
  "objectType": "Group",
  "eventType": "SurveyResponse",
  "eventId": "3e49b367-acf6-48a7-a675-6bf4d372a070",
  "data": {
   "actionId": "920f9802-62dafb-9bc2-8d3ba5c43609",
    "groupId": "8c291050-9be8-4d6-97f5-bb7013930027",
    "responseId": "420e9ef0-2a6d-405-a2bf-2688648ce79a",
    "isUpdateResponse": false,
    "responder": "+91xxxxxxxxx",
    "responderName": "Robin Richard",
    "responderProfilePic": "https://mobileonlyapps.blob.core.windows.net/72e29591-f391-4e7b-84eb-4e228406fb9b/c34afc0d53614ae29285d08e6409e416.jpg",
    "isAnonymous": false,
    "responseDetails": {
      "responseWithQuestions": [
        {
          "title": "1",
          "type": "Text",
          "options": [],
          "answer": "1"
        },
        {
          "title": "2",
          "type": "AttachmentList",
          "options": [],
          "answer": [
            {
              "mediaUrl": "https://cdn.inc-000.kms.osi.office.net/att/9841be297131449fba1123ec8545ab30fa72c2017555ba4bcd4ac18d5f7850b4.jpg?sv=2015-12-11&amp;sr=b&amp;sig=Egd4wDmAfGrIoklLj70SrV7D3QtwtMEWQx673U%3D&amp;st=2018-03-23T09:26:24Z&amp;se=2292-01-06T10:26:24Z&amp;sp=r",
              "mediaFileName": "IMG_18-03-23_155619990_1.jpg"
            }
          ]
        },
        {
          "isInvisible": true,
          "title": "ResponseTime",
          "type": "DateTime",
          "options": [],
          "answer": 1521800782956
        }
      ]
    }
  },
  "context": "Any data which is required to be returned in callback",
  "fromUser": "+91xxxxxxxx",
  "fromUserId": "72e91-f3-4e7b-84eb-4e228406fb9b",
  "fromUserName": "Robin Richard",
  "fromUserProfilePic": "https://mobileonlyapps.blob.core.windows.net/72e29591-4e7b-84eb-4e228406fb9b/c34afc0d53614ae29285d08e6409e416.jpg"
}
```


### data for event 'MemberAdded' / 'MemberRemoved'
| Parameter | Type | Description |
| :---: | :---: | :--- |
| member | String | Phone Number of the added Member |
| memberName | String | Name of the added Member |
| type | String | Membership role of the added member |
| memberProfilePic | url | url of the assignee's profile pic |





#### Sample webHook response for 'MemberAdded' /'MemberRemoved'
```javascript
{
  "objectId": "8c2950-9be8-45d6-97f5-bb7013930027",
  "objectType": "Group",
  "eventType": "JobResponse",
  "eventId": "3e49b367-acf6-48a7-a675-6bf4d372a070",
  "data": {
    "member": "+91xxxxxxxx",
    "memberName": "Jan Decker",
    "memberProfilePic": "https://mobileonlyapps.blob.core.windows.net/polymer-7ebb8d90e1324b5cbd61d1e10a30ada7/bbac582a4364860679d40fda7c6b.jpg",
    "type": "Member"
  },
  "context": "Any data which is required to be returned in callback",
  "fromUser": "+91xxxxxxxx",
  "fromUserId": "72e91-f3-4e7b-84eb-4e228406fb9b",
  "fromUserName": "Robin Richard",
  "fromUserProfilePic": "https://mobileonlyapps.blob.core.windows.net/72e29591-4e7b-84eb-4e228406fb9b/c34afc0d53614ae29285d08e6409e416.jpg"
}
```

