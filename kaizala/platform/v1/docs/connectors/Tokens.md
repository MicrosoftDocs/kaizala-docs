# Authentication Mechanism

## Authentication for Kaizala Connectors

Kaizala Connectors will soon be integrated with Azure Active Directory (Azure AD) to provide secure sign in and authorization.

As an interim solution, we have implemented a custom token based authorization mechanism based on the OAUTH framework. This mechanism uses the concept of Refresh and Access Tokens
to manage access authorization for the Kaizala Platform APIs.

*   Refresh tokens carry the information necessary to get a new access token. They need to be passed on to the Token Service when an access token expires, or when an access token needs to be generated for the first time. Refresh tokens for Kaizala Connectors also expire and have an expiration time of 365 days. 

*   Access tokens carry the necessary information to access a Kaizala resource. A 3rd party client needs to pass an access token to the Kaizala Platform with each API request. Access tokens for Kaizala Connectors have an expiration time of 24 hours.


|              | Details           | How to generate   | Expiration Time    |
| :---: | :---: | :---: | :---: |
| Refresh Token  | Carry the information necessary to get a new access token     | Group Admin generates by granting access to his/her group   | 365 days           |
| Access Token   | Carry the necessary information to access a Kaizala resource  | Developer uses refresh Token & other connector details to query Kaizala API endpoint to generate Access Token    | 24 hours            |

*   Refresh tokens can be invalidated by the server in two ways - by generating new Refresh Tokens for the same Kaizala Connector or deleting the corresponding Kaizala Connector altogether.

## Different types of Refresh Tokens

Kaizala Connectors allow options to generate two different types of Refresh Token.

|              |   Tools to generate  | Scope of Access   | Who can generate | Details |
| :---: | :---: | :---: | :---: | :---: |
| Group Token  | Kaizala Management Portal     | Selected Group   | Group/Tenant Admin |Using this token, developer can perform operations that a group admin has permissions for in that group |
| User Token   | Kaizala Management Portal  | All groups that a user is member of | Any user | If user is Tenant Admin, this token carries tenant-level access. For others, the token can be used to access groups according to his/her access |
| User Token   | Using oAuth | All groups that a user is member of | Any user |Using this token, developer can perform operations that a user has access to in a particular group.|

*   In case of User Tokens, single token provides access to all groups a user is part of
*   For a single connector, developers can generate tokens for multiple groups


## Methods to generate Access Token

Kaizala presents 2 method to generate Access tokens
* Using API
* Using oAuth
