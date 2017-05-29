## /members
API end-point to add or delete members from conversation groups inside Kaizala.

### GET /members

    GET https://{api_root}/groups/{groupId}/members

##### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| URL Path Parameter | groupId | String | No | GUID representing the groupId of the specific group resource |
| HTTP Header | applicationId | String | No | ID associated with the Connector that was registered by the developer – on behalf of which the API calls need to be made |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |

##### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| members | JSON Array | Array of JSON objects each representing a member of the group |

###### Sample JSON Response

```javascript
{
  "members": [
    {
      "id": "4deffa08-guid-4b87-8c2f-d944565f5f31",
      "role": "Admin",
      "mobileNumber": "+919652000000",
      "isProvisioned": true
    },
    {
      "id": "2e20e9ac-guid-47bd-abac-1f5236004684",
      "role": "Member",
      "mobileNumber": "+919652000001",
      "isProvisioned": false
    }
  ]
}
```

### PUT /members

    PUT https://{api_root}/groups/{groupId}/members

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
| members | String Array | Array of well-formatted phone numbers of new members to be added |

###### Sample JSON Request

```javascript
{
  "members": [
      "+91000000000",
      "+91900000000"
  ]
}
```

##### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| result | Boolean | True when all phone numbers have succesfully been added to the group |

###### Sample JSON Response

```javascript
{
    "result": "true"
}
```

### DELETE /members

    DELETE https://{api_root}/groups/{groupId}/members/{memberId}

##### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| URL Path Parameter | groupId | String | No | GUID representing the groupId of the specific group resource |
| URL Path Parameter | memberId | String | No | GUID representing the memberId of the specific member |
| HTTP Header | applicationId | String | No | ID associated with the Connector that was registered by the developer – on behalf of which the API calls need to be made |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |
| HTTP Header | Content-Type | String | No | value: application/json |

##### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| result | Boolean | True when the specified member has succesfully been removed from the group |

###### Sample JSON Response

```javascript
{
    "result": "true"
}
```