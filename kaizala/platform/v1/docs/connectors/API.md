# Kaizala API Documentation

Before you get started, please refer to [Setup for using the Kaizala Connectors](setup.md)

## Root Domain

The root domain for invoking the Kazaila APIs is:

    https://api.kaiza.la/v1/

### Access Token

As a developer, you would have a Connector ID, Secret and a Refresh Token passed on to you by the respective group Admin. You will need to use the following end-point to get an access token (both the first time & later when the access token expires):

    GET https://{api_root}/accessToken

##### Request Parameters

|            	| Parameter         	| Type   	| Optional? 	| Description |
| :---: | :---: | :---: | :---:	| :--- |
| HTTP Header 	| `applicationId`     	| String 	| No        	| ID associated with the Connector 	|
| HTTP Header 	| `applicationSecret` 	| String 	| No        	| Secret associated with the Connector                                                                                     	|
| HTTP Header 	| `refreshToken`      	| String 	| No        	| refreshToken shared by the Kaizala Group Admin when the respective Connector was granted access to the group             	|

##### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| `accessToken` | String | On successful auth, an application token is returned that can be used for making subsequent API calls |

##### Sample JSON Response

```javascript
{ 
    "accessToken" :"qwassasaswadheenqqwertyasdfghjkl"
}
```

### API End-points

The Kaizala API runs on the secure Microsoft Azure cloud, and interacts with the Kaizala platform to perform various actions for end users.
The API works with the following Kaizala resources:

*   [/groups](groups.md)
*   [/members](members.md)
*   [/messages](messages.md)
*   [/media](media.md)
*   [/actions](actions.md)

