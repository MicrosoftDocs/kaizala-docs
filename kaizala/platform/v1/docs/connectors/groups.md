## /groups
API end-point to interact with the conversation groups inside Kaizala. Current scope is to support retrieving group information via GET requests only.

### GET /groups

    GET https://{api_root}/groups

##### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |

##### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| groups | JSON Object Array | Array of groups that the user has access to with the accessToken |

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
      "groupId": "853654b2-5874-462d-b709-0c4e43a7083f",
      "groupImageUrl": "{sample group image URL here}",
    }
  ]
}
```

### GET /groups/{groupId}

You can get additional details about a specific resource member (a group here) by specifying the identifier as a URL path parameter.

    GET https://{api_root}/groups/{groupId}

##### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| URL Path Parameter | groupId | String | No | GUID representing the groupId of the specific group resource |
| HTTP Header | applicationId | String | No | ID associated with the Connector that was registered by the developer – on behalf of which the API calls need to be made |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |

##### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| groups | JSON Object Array | Array of groups that the user has access to with the accessToken |

JSON structure for each individual group in the array groups[]:

| Parameter | Type | Description |
| :---: | :---: | :--- |
| groupId | String | GUID associated with the group |
| groupName | String | Name of the group |
| groupImageURL | String | String specifying the URL of the group profile picture |
| hasSubGroups | Boolean | True if this group has other groups as members as in a hierarchy |
| userCount | Numeric | Total number of users under this group across the hierarchy |
| currentLevelUserCount | Numeric | Total number of individual members of the group at the current level |

###### Sample JSON Response

```javascript
{
  "groups": [
    {
      "groupName": "Sample group name",
      "groupId": "853654b2-5874-462d-b709-0c4e43a7083f",
      "groupImageUrl": "{sample group image URL here}",
      "hasSubGroups": true,
      "userCount": 200,
      "currentLevelUserCount": 10
    }
  ]
}
```

