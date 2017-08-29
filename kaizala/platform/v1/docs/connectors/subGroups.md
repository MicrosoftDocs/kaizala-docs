## /subGroups
API end-point to interact with the conversation sub-groups inside Kaizala. Current scope is to support retrieving and creating sub groups.

### GET /subGroups

    GET https://{api_root}/groups/{groupId}/subGroups

##### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| HTTP Header | applicationId | String | No | ID associated with the Connector that was registered by the developer – on behalf of which the API calls need to be made |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |
| URL Path Parameter | groupId | String | No | GUID representing the groupId of the specific group resource |
| URL Query Parameter | fetchAllGroups | Boolean | Yes | Parameter to specify if you would like to fetch all the subGroups across the hierarchy |

##### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| groups | JSON Object Array | Array of groups with the list of subGroups if any |

######  JSON structure for each individual group in the array groups[]:

| Parameter | Type | Description |
| :---: | :---: | :--- |
| groupId | String | GUID associated with the group |
| groupName | String | Name of the group |
| groupImageURL | String | String specifying the URL of the group profile picture |

###### Sample JSON Response

```javascript
{
  "groups": [
    {
      "groupName": "Sample group name",
      "groupId": "853654b2-guid-462d-b709-0c4e43a7083f",
      "groupImageUrl": "{sample group image URL here}",
      "subGroups": [
          {
            "groupName": "Sample sub group name",
            "groupId": "853654b2-guid-462d-b709-0c4e43a7083f",
            "groupImageUrl": "{sample sub group image URL here}",
          }
      ]
    }
  ]
}
```

### POST /subGroups

    POST https://{api_root}/groups/{groupId}/subGroups

##### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| HTTP Header | applicationId | String | No | ID associated with the Connector that was registered by the developer – on behalf of which the API calls need to be made |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |
| URL Path Parameter | groupId | String | No | GUID representing the groupId of the specific group resource |

##### Request body

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| Name | String | No | Name of the sub group |
| groupImageURL | String | Yes | Media URL of the group image; Image needs to be uploaded through the /media path |
| members | Array | Yes | String array of well-formatted phone numbers |
| welcomeMessage | Array | No | String array of well-formatted phone numbers  |
| addUserToGroup | Boolean | Yes | Set to False if the calling user should not be added to the group by default  |


###### Sample JSON Request

```javascript
{
  "Name": "Test Group",
  "groupImageUrl": "",
  "members": [ "+919652000000", "+919910000005"],
  "welcomeMessage": "Hello",
  "addUserToGroup": false
}
```

##### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| groupId | String | GUID representing the group created |
| groupName | String | Name of the group created |


###### Sample JSON Response

```javascript
{
    "groupId": "853654b2-5874-462d-b709-0c4e43a7083f",
    "groupName": "Test Group"
}
```
