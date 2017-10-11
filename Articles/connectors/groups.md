---
title: /groups
description: Reference Article for API to query group data
topic: Reference
author: nitinjms
---
## /groups
API end-point to interact with the conversation groups inside Kaizala.

### POST /groups

    Post {endpoint-url}/v1/groups

##### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |
| HTTP Header | Content-Type | String | No | "application/json" |

##### Request body

| Parameter | Type | Optional? | Description |
| :---: | :---: | :--- | :--- |
| name | String | No | Group name |
| welcomeMessage | String | No | Welcome message which will be displayed to new group member |
| members | String[] | Yes | Mobile number(with country code) of members to be added. Default: Access token's user will be added as admin of the group |
| groupType | String | Yes | Enum: Group/ConnectGroup. ConnectGroup will create Managed Public group. Default: Group |

###### Sample JSON Request for Create Group

```javascript
{
    name:"Kaizala Test group",
    welcomeMessage:"Welcome to group created programmatically",
    members:["+911099999999"],
    groupType: "Group"
}
```

##### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| groupName | String | Group name |
| groupId | String | Group Identifier which can be used in subsequent api calls |
| membersAdded | bool | True if all members are successfully added |

###### Sample JSON Response

```javascript
{
   "groupName": "Kaizala Test group",
   "groupId": "853654b2-5874-462d-b709-0c4e43a7083f",
   "membersAdded": true
}
```


### GET /groups

    GET {endpoint-url}/v1/groups

##### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |
| Query parameter | showDetail | bool | Yes | Default: false. True to return all group details |
| Query parameter | fetchAllGroups | bool | Yes | Default: false. True to return all parent and sub groups |

##### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| groups | JSON Object Array | Array of groups that the user has access to with the accessToken |

######  JSON structure for each individual group in the array groups[]:

| Parameter | Type | Description |
| :---: | :---: | :--- |
| groupId | String | Group Identifier |
| groupName | String | Name of the group |
| groupImageURL | String | String specifying the URL of the group profile picture |
| hasSubGroups | bool | True if the group has subgroups |
| hasParentGroups | bool | True if the group has parent groups |
| isMappedToTenant | bool | True if the group is Organisation group |
| groupType | String | Group/ConnectGroup. ConnectGroup if the group in Managed Public group |
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
      "hasSubGroups": false,
      "hasParentGroups": false,
      "callerRole": "Admin",
      "currentLevelSubGroupCount": 0,
      "currentLevelParentGroupCount": 0,
      "userCount": 2,
      "uniqueUserCount": 0,
      "currentLevelUserCount": 2,
      "currentLevelUnProvisionedUserCount": 0,
      "unProvisionedUserCount": 0,
      "isMappedToTenant": false,
      "groupType": "Group",
      "isDuplicate": false,
      "isEditable": true,
      "isDetailsReadable": true
    }
  ]
}
```

### GET /groups/{groupId}

You can get details about a specific resource member (a group here) by specifying the identifier as a URL path parameter

    GET {endpoint-url}/groups/{groupId}

##### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| URL Path Parameter | groupId | String | No | GUID representing the groupId of the specific group resource |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |

##### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| groups | JSON Object Array | Array of groups that the user has access to with the accessToken |

JSON structure for each individual group in the array groups[]:

| Parameter | Type | Description |
| :---: | :---: | :--- |
| groupId | String | Group Identifier |
| groupName | String | Name of the group |
| groupImageURL | String | String specifying the URL of the group profile picture |
| hasSubGroups | bool | True if the group has subgroups |
| hasParentGroups | bool | True if the group has parent groups |
| isMappedToTenant | bool | True if the group is Organisation group |
| groupType | String | Group/ConnectGroup. ConnectGroup if the group in Managed Public group |
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

