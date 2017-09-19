# Kaizala API Documentation

Before you get started, please refer to [Setup for using the Kaizala Connectors](setup.md)

## Root Domain

The root domain for invoking the Kaizala APIs is:

    {endpoint-url}
    
|            	| Parameter         	| Type   	| Optional? 	| Description |
| :---: | :---: | :---: | :---:	| :--- |
| Endpoint url 	| `endpoint-url`     	| String 	| No        	| On successful auth while generating access tokens, an endpoint url is returned that should be used as api-base-url for making subsequent API calls	|


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

### Postman Collection

In order to test our APIs, as well as understand Kaizala API schema, you can import postman collection containing samples and schema for all the Microsoft Kaizala apis:

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/f68a8abec784cc00b0b9#?env%5BKaizala-APIs-environment%5D=W3siZW5hYmxlZCI6dHJ1ZSwia2V5IjoibW9iaWxlLW51bWJlciIsInZhbHVlIjoiIiwidHlwZSI6InRleHQifSx7ImVuYWJsZWQiOnRydWUsImtleSI6ImFjY2Vzcy10b2tlbiIsInZhbHVlIjoiIiwidHlwZSI6InRleHQifSx7ImVuYWJsZWQiOnRydWUsImtleSI6InRlc3QtZ3JvdXAtaWQiLCJ2YWx1ZSI6IiIsInR5cGUiOiJ0ZXh0In0seyJlbmFibGVkIjp0cnVlLCJrZXkiOiJtb2JpbGUtbnVtYmVyLTIiLCJ2YWx1ZSI6Iis5MTExOTk5OTk5OTkiLCJ0eXBlIjoidGV4dCJ9LHsiZW5hYmxlZCI6dHJ1ZSwia2V5IjoiYXBpLXJvb3QiLCJ2YWx1ZSI6Imh0dHBzOi8vYXBpLmthaXphLmxhIiwidHlwZSI6InRleHQifSx7ImVuYWJsZWQiOnRydWUsImtleSI6ImFwcGxpY2F0aW9uLWlkIiwidmFsdWUiOiIiLCJ0eXBlIjoidGV4dCJ9LHsiZW5hYmxlZCI6dHJ1ZSwia2V5IjoiYXBwbGljYXRpb24tc2VjcmV0IiwidmFsdWUiOiIiLCJ0eXBlIjoidGV4dCJ9LHsiZW5hYmxlZCI6dHJ1ZSwia2V5IjoiZW5kcG9pbnQtdXJsIiwidmFsdWUiOiJodHRwczovL2luYy0wMDEuS2FpemFsYU1lc3NhZ2luZy5vc2kub2ZmaWNlLm5ldCIsInR5cGUiOiJ0ZXh0In0seyJlbmFibGVkIjp0cnVlLCJrZXkiOiJyZWZyZXNoLXRva2VuIiwidmFsdWUiOiIiLCJ0eXBlIjoidGV4dCJ9LHsiZW5hYmxlZCI6dHJ1ZSwia2V5IjoidGVzdC1wdWJsaWMtZ3JvdXAtaWQiLCJ2YWx1ZSI6IiIsInR5cGUiOiJ0ZXh0In0seyJlbmFibGVkIjp0cnVlLCJrZXkiOiJ0ZXN0LXN1Yi1ncm91cC1pZCIsInZhbHVlIjoiIiwidHlwZSI6InRleHQifSx7ImVuYWJsZWQiOnRydWUsImtleSI6Im1vYmlsZS1udW1iZXItMyIsInZhbHVlIjoiKzkxMTA5OTk5OTk5IiwidHlwZSI6InRleHQifSx7ImVuYWJsZWQiOnRydWUsImtleSI6InRlc3QtYWN0aW9uLWlkIiwidmFsdWUiOiIiLCJ0eXBlIjoidGV4dCJ9LHsiZW5hYmxlZCI6dHJ1ZSwia2V5IjoidGVzdC1zdXJ2ZXktaWQiLCJ2YWx1ZSI6IiIsInR5cGUiOiJ0ZXh0In0seyJlbmFibGVkIjp0cnVlLCJrZXkiOiJ0ZXN0LXdlYmhvb2staWQiLCJ2YWx1ZSI6IiIsInR5cGUiOiJ0ZXh0In1d)

Please set following environment variables in "Kaizala-APIs-environment" before running the postman project:
* mobile-number : Your mobile number which will be used for invoking apis
* application-id : ID associated with the Connector
* application-secret : Secret associated with the Connector

Other enviroment variables will be auto-populated while trying the apis in sequence mention in Postman Project. 
