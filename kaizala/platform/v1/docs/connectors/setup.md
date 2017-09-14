# Setup for using the Kaizala Connectors

## Personas

*   **Developer:** In-house or 3rd party developing applications for the organization – who need to integrate Kaizala into the organization’s business processes. Developer does not have access to the end-user while developing the application (differs from an Admin).
*   **Admin:** User who is part of the end-groups and is an administrator. Is expected to perform group management tasks.
*   **User:** Kaizala end users

## Pre-req to set-up

*   As a **developer:**
    *   An Office365 account
    *   A Kaizala registered phone number
    *   Dev set-up (any platform) to invoke REST API
*   As an **admin**
    *   An Office365 account
    *   A Kaizala registered phone number
    *   Admin of a conversation group inside Kaizala with the registered phone number
*   As a **user**
    *   A Kaizala registered phone number
    *   Member of a conversation group inside Kaizala with the registered phone number

## Authentication for Kaizala Connectors

Kaizala Connectors will soon be integrated with Azure Active Directory (Azure AD) to provide secure sign in and authorization.

As an interim solution, we have implemented a custom token based authorization mechanism based on the OAUTH framework. This mechanism uses the concept of Refresh and Access Tokens
to manage access authorization for the Kaizala Platform APIs.

*   Access tokens carry the necessary information to access a Kaizala resource. A 3rd party client needs to pass an access token to the Kaizala Platform with each API request. Access tokens for Kaizala Connectors have an expiration time of 24 hours.
*   Refresh tokens carry the information necessary to get a new access token. They need to be passed on to the Token Service when an access token expires, or when an access token needs to be generated for the first time. Refresh tokens for Kaizala Connectors also expire and have an expiration time of 365 days. Refresh tokens can be invalidated by the server in two ways - by generating new Refresh Tokens for the same Kaizala Connector or deleting the corresponding Kaizala Connector altogether.

## Set-up steps (Developer & Group admin)

There are four major infrastructure components involved in working with the Kaizala Platform API:

*   **Connectors:** All 3rd party systems that need to integrate with Kaizala need to be registered with the Kaizala platform as a “Connector” and get API Tokens corresponding to the Connector.
*   **Kaizala Management Portal:** A portal to register the respective 3rd party Connectors – and provide them access to Kaizala Conversation groups.
*   **Token Service:** A URL end-point which needs to be called by the 3rd party apps to get Access Tokens.
*   **Platform Service:** A URL end-point which exposes specific resources to perform various actions inside Kaizala.
*   **Step 1: Developer registers a Connector**

    *   Developer navigates to Kaizala Management Portal @ https://manage.kaiza.la/
    *   Log in using an existing Office365 account
    *   Register a phone number on the portal by tapping on “Add a Phone Number”
        *   Enter Phone number
        *   Tap on “Generate PIN”
        *   Verify the PIN received via an SMS on the specified phone number
    *   Tap on “Connectors” in the left menu
    *   Tap on “Add Connector”
    *   Register a connector for the 3rd party system that will use the API
        *   Enter the name of the Connector and other details. Tap on Continue
        *   Select permissions that is intended for the Connector to have access to
        *   Tap on Create Connector
    *   Note the ID & Secret that get generated and displayed on the portal

*   **Step 2: Group Admin “grants” the Connector access to his/her group**

    *   Admin navigates to Kaizala Management Portal @ https://manage.kaiza.la/
    *   Log in using an existing Office365 (SKU TBD) account
    *   Register a phone number on the portal by tapping on “Add a Phone Number”
        *   Enter Phone number
        *   Tap on “Generate PIN”
        *   Verify the PIN received via an SMS on the specified phone number
    *   Tap on “Groups” in the left menu
    *   Tap on the group name which needs to be accessed by the Connector
    *   Tap on “Connectors”
    *   In the drop-down, select the Connector that you want to grant access to
    *   Tap on “Add Connector”
    *   Note the Refresh Token that gets generated and displayed on the portal

*   **Step 3: Group Admin shares the Refresh Token with the App Developer**

    *   Admin needs to manually share the refresh token received in Step 2 with the app developer

*   **Step 4: App Developer calls the Kaizala Platform Rest API using the token**

    *   Developer can now use the token to call the REST API (more info below)


Next: [API Documentation](API.md)
