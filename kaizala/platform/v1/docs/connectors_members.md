## /members
API end-point to add members to conversation groups inside Kaizala. Current scope is to support adding of members only.

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