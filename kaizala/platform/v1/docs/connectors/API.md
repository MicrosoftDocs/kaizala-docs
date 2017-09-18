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
| HTTP Header 	| `applicationSecret` 	| String 	| No        	| Secret associated with the Connector |
| HTTP Header 	| `refreshToken`      	| String 	| No        	| refreshToken shared by the Kaizala Group Admin when the respective Connector was granted access to the group |

##### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| `accessToken` | String | On successful auth, an application token is returned that can be used for making subsequent API calls |
| `endpointUrl` | String | On successful auth, an endpoint url is returned that should be used as api-base-url for making subsequent API calls |
| `accessTokenExpiry` | Long | It indicates the expiry time for accessToken in epoch time(milliseconds) |

##### Sample JSON Response

```javascript
{ 
    "accessToken" :"qwassasaswadheenqqwertyasdfghjkl",
    "endpointUrl": "https://inc-001.KaizalaMessaging.osi.office.net",
    "accessTokenExpiry": 1505470472895,
}
```

### API End-points

The Kaizala API runs on the secure Microsoft Azure cloud, and interacts with the Kaizala platform to perform various actions for end users.
The API works with the following Kaizala resources:

*   [/groups](groups.md)
*   [/subGroups](subGroups.md)
*   [/members](members.md)
*   [/messages](messages.md)
*   [/media](media.md)
*   [/actions](actions.md)

### WebHooks

The Microsoft Kaizala API also provides a way for developers to register for specific events within the Kaizala platform via WebHooks.

*   [/webhook](webHooks.md)

### Postman COllection

You can import postman collection containing samples and schema for all the Microsoft Kaizala apis:

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/f68a8abec784cc00b0b9#?env%5BKaizala-APIs-environment%5D=W3siZW5hYmxlZCI6dHJ1ZSwia2V5IjoibW9iaWxlLW51bWJlciIsInZhbHVlIjoiIiwidHlwZSI6InRleHQifSx7ImVuYWJsZWQiOnRydWUsImtleSI6ImFjY2Vzcy10b2tlbiIsInZhbHVlIjoiIiwidHlwZSI6InRleHQifSx7ImVuYWJsZWQiOnRydWUsImtleSI6InRlc3QtZ3JvdXAtaWQiLCJ2YWx1ZSI6IiIsInR5cGUiOiJ0ZXh0In0seyJlbmFibGVkIjp0cnVlLCJrZXkiOiJtb2JpbGUtbnVtYmVyLTIiLCJ2YWx1ZSI6Iis5MTExOTk5OTk5OTkiLCJ0eXBlIjoidGV4dCJ9LHsiZW5hYmxlZCI6dHJ1ZSwia2V5IjoiYXBpLXJvb3QiLCJ2YWx1ZSI6Imh0dHBzOi8vYXBpLmthaXphLmxhIiwidHlwZSI6InRleHQifSx7ImVuYWJsZWQiOnRydWUsImtleSI6ImFwcGxpY2F0aW9uLWlkIiwidmFsdWUiOiIiLCJ0eXBlIjoidGV4dCJ9LHsiZW5hYmxlZCI6dHJ1ZSwia2V5IjoiYXBwbGljYXRpb24tc2VjcmV0IiwidmFsdWUiOiIiLCJ0eXBlIjoidGV4dCJ9LHsiZW5hYmxlZCI6dHJ1ZSwia2V5IjoiZW5kcG9pbnQtdXJsIiwidmFsdWUiOiJodHRwczovL2luYy0wMDEuS2FpemFsYU1lc3NhZ2luZy5vc2kub2ZmaWNlLm5ldCIsInR5cGUiOiJ0ZXh0In0seyJlbmFibGVkIjp0cnVlLCJrZXkiOiJyZWZyZXNoLXRva2VuIiwidmFsdWUiOiIiLCJ0eXBlIjoidGV4dCJ9LHsiZW5hYmxlZCI6dHJ1ZSwia2V5IjoidGVzdC1wdWJsaWMtZ3JvdXAtaWQiLCJ2YWx1ZSI6IiIsInR5cGUiOiJ0ZXh0In0seyJlbmFibGVkIjp0cnVlLCJrZXkiOiJ0ZXN0LXN1Yi1ncm91cC1pZCIsInZhbHVlIjoiIiwidHlwZSI6InRleHQifSx7ImVuYWJsZWQiOnRydWUsImtleSI6Im1vYmlsZS1udW1iZXItMyIsInZhbHVlIjoiKzkxMTA5OTk5OTk5IiwidHlwZSI6InRleHQifSx7ImVuYWJsZWQiOnRydWUsImtleSI6InRlc3QtYWN0aW9uLWlkIiwidmFsdWUiOiIiLCJ0eXBlIjoidGV4dCJ9LHsiZW5hYmxlZCI6dHJ1ZSwia2V5IjoidGVzdC1zdXJ2ZXktaWQiLCJ2YWx1ZSI6IiIsInR5cGUiOiJ0ZXh0In0seyJlbmFibGVkIjp0cnVlLCJrZXkiOiJ0ZXN0LXdlYmhvb2staWQiLCJ2YWx1ZSI6IiIsInR5cGUiOiJ0ZXh0In1d)

Please set following environment variables in "Kaizala-APIs-environment" before running the postman project:
* mobile-number : Your mobile number which will be used for invoking apis
* application-id : ID associated with the Connector
* application-secret : Secret associated with the Connector

Other enviroment variables will be auto-populated while trying the apis in sequence mention in Postman Project. 
