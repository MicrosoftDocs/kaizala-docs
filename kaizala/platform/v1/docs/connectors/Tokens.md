# Authentication Mechanism

Before you get started, please refer to [Setup for using the Kaizala Connectors](setup.md)

## Authentication for Kaizala Connectors
 
We have implemented a custom token based authorization mechanism. This mechanism uses the concept of Refresh and Access Tokens to manage access authorization for the Kaizala Platform APIs.
*   Refresh tokens carry the information necessary to get a new access token. They need to be passed on to the Token Service when an access token expires, or when an access token needs to be generated for the first time. Refresh tokens for Kaizala Connectors have an expiration time of 365 days. 

*   Access tokens carry the necessary information to access a Kaizala resource. A 3rd party client needs to pass an access token to the Kaizala Platform with each API request. Access tokens for Kaizala Connectors have an expiration time of 24 hours.


|              | Details           | How to generate   | Expiration Time    |
| :---: | :---: | :---: | :---: |
| Refresh Token  | Carry the information necessary to get a new access token     | Different ways to generate refresh token are documented in next section below | 365 days           |
| Access Token   | Carry the necessary information to access a Kaizala resource  | Developer uses refresh Token & other connector details to query Kaizala API endpoint to generate Access Token    | 24 hours            |

*   Refresh tokens can be invalidated by the server in two ways - by generating new Refresh Tokens for the same Kaizala Connector or deleting the corresponding Kaizala Connector altogether.
## Different types of Refresh Tokens

Kaizala Connectors allow options to generate two different types of Refresh Token. Users token can be generated either through Kaizala Management Portal or oAuth.

|              |   Tools to generate  | Scope of Access   | Who can generate | Details |
| :---: | :---: | :---: | :---: | :---: |
| Group Token  | Kaizala Management Portal     | Selected Group   | Group/Tenant Admin |Using this token, developer can perform operations that a group admin has permissions for in that group |
| User Token   | Kaizala Management Portal  | All groups that a user is member of | Any user | If user is Tenant Admin, this token carries tenant-level access. For others, the token can be used to access groups according to his/her access |
| User Token   | Using OAuth 2.0, Using APIs | All groups that a user is member of | Any user |Using this token, developer can perform operations across all groups.|

*   In case of User Tokens, single token provides access to all groups a user is part of
*   For a single connector, developers can generate tokens for multiple groups

Once Refresh Token is provided by either Group-Admin or user to the Developer, it should be used to generate Access Token.

Kaizala presents two method to generate Refresh tokens programatically
* Using API (Will add soon)
* Using OAuth (Will add soon)

## Methods to generate Access Token

As a developer, you would now have a Connector ID, Secret and a Refresh Token that should be passed on to you. Using this, you can generate an access token.

### Generate Access Token using API

The root domain for invoking the Kazaila APIs is:

    https://api.kaiza.la/v1/

You will need to use the following end-point to get an access token (both the first time & later when the access token expires):

    GET https://{api_root}/accessToken

##### Request Parameters

|            	| Parameter         	| Type   	| Optional? 	| Description |
| :---: | :---: | :---: | :---:	| :--- |
| HTTP Header 	| `applicationId`     	| String 	| No        	| ID associated with the Connector 	|
| HTTP Header 	| `applicationSecret` 	| String 	| No        	| Secret associated with the Connector |
| HTTP Header 	| `refreshToken`      	| String 	| No        	| refreshToken shared by the Kaizala Group Admin when the respective Connector was granted access to the group 

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
### Generate Access Token using oAuth 2.0

#### Steps to generate Access Token using oAuth 2.0
*    **Step 1:** Create/Update a connector on Kaizala Management Portal to include redirect url
     *    In the connector that you are using, please ensure that you have entered a redirect url while creating the connector. If not, please update redirect url
     *    For testing purposes, you can use the below postman callback URL, which just gives you a page with the code. 
        
          `https://www.getpostman.com/oauth2/callback`
 
*    **Step 2:** Type below url in the Browser and press Enter

          `https://ds.kaiza.la/api/Oauth/Authorize?client_id={{ConnectorID}}&redirect_uri={{re-directURL}}`
      
      *   Please ensure that you have entered 'client_id' & 'redirect_uri' correctly
       ##### Request Parameters

       |            	| Parameter         	| Type   	| Optional? 	| Description |
       | :---: | :---: | :---: | :---:	| :--- |
       | HTTP Header 	| `client_id`     	| String 	| No        	| ID associated with the Connector 	|
       | HTTP Header 	| `redirect_uri` 	| String 	| No        	| Secret associated with the Connector |

     *    For example, sample url would be
     
            `https://ds.kaiza.la/api/Oauth/Authorize?client_id=2AB9B82044683484EE9D958E7&redirect_uri=https://www.getpostman.com/oauth2/callback`


*    **Step 3:** Sign-in to Kaizala and generate 'code'
     *   As soon as you press enter in Step 2, you shall be taken to Kaizala sign-in page
     *   Authenticate yourself using your registered Kaizala number
     *   After you successfully sign-in, you will be re-directed to the re-direct url with 'code' as query parameter in callback url
     *   Note down the returned 'code' 
     
*    **Step 4:** Use code to generate Access Token
     *   Make below API call to generate Access Token
     
         `POST https://ds.kaiza.la/api/oauth/token `
     
     ##### Request Parameters

       |            	| Parameter         	| Type   	| Optional? 	| Description |
       | :---: | :---: | :---: | :---:	| :--- |
       | HTTP Header 	| `client_id`     	| String 	| No        	| ID associated with the Connector 	|
       | HTTP Header 	| `client_secret` 	| String 	| No        	| Secret associated with the Connector |
       | HTTP Header 	| `code` 	| String 	| No        	| Code that has been returned in the re-direct url's query parameter |
     
You will receive   accessToken, endpointUrl, accessToken Expiry as part of the response.

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

Next: [API Documentation](API.md)
