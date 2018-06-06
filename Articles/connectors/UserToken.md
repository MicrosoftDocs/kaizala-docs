# Generate tenant-level user token

Tenant-level user refresh token can be used to grant access to all the user's groups where user is an admin. 
For a Tenant user, this token grants access to all the groups for an organization.

## Steps to generate Tenant-level user token
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

*   **Step 2: Tenant User “grants” the Connector access to all groups that he is admin to**

    *   User navigates to Kaizala Management Portal @ https://manage.kaiza.la/
    *   Log in using an existing Office365 (SKU TBD) account
    *   Register a phone number on the portal by tapping on “Add a Phone Number”
        *   Enter Phone number
        *   Tap on “Generate PIN”
        *   Verify the PIN received via an SMS on the specified phone number
    *   Tap on “Connectors” in the left menu
    *   Tap on the connector name which needs to be accessed by the Connector
    *   Tap on “Generate user token”
    *   Note the Refresh Token that gets generated and displayed on the portal

*   **Step 3: User shares the Refresh Token with the App Developer**

    *   Admin needs to manually share the refresh token received in Step 2 with the app developer

*   **Step 4: App Developer calls the Kaizala Platform Rest API to generate Access Token**

    *   Developer can now use the Refresh token. a Connector ID and Connector Secret to call the REST API inorder to generate Access Token (more info below)

