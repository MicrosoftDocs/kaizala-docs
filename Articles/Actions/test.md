# Test and Debug

Once Custom Action development is done, you may want to test it to see if its working fine end to end and fix any bugs that you discover in testing. As well as in some cases, you would like to debug the html views for any possible issues.

The Kaizala Management Portal provides a convenient way to test & debug your new Kaizala Actions. 
>   You will need an active Kaizala Pro or Office365 Organizational subscription to access the Management Portal.

# Pre-Requisite to enable test mode for your Action

In your ‘Package.json’ file for your Action
*   Add a flag **‘forTesting’** under ‘dials’ tag. Please find the part of the sample code below. 
```
     "dials": {
   	    "isLocalised": true,
        "forTesting": true
     },
```
*   Tag **‘id’** should be different from any other Action that has been uploaded

> In order to test an action package, you **don’t** need any approval

**Note:** After you have tested your Action and you are satisfied with the functionality, you need to follow below steps before sending for approval:
* 	Remove flag ‘forTesting’ under ‘dials’ tag in ‘Package.json’ file
* 	Change your tag ‘id’, as it should be different from the test Action id

# Steps to test a Action

After you have satisfied the pre-requisites, you can test your action by following below steps

* 	Navigate to the Kaizala Management Portal @ https://manage.kaiza.la/
* 	Log in using an existing Office365 account
*   Register a phone number on the portal by tapping on “Add a Phone Number”
*   Tap on "Actions" on the left menu
*   Tap on "Import a new Action"
*   Upload your package
*   After successful upload, you are taken to the uploaded ‘Action Details’ page
*   On this page, you can choose to Add your Action to groups for testing purposes
    *   The group you select must be a flat group (i.e. with no sub-groups)
    *   The group must have a managed palette for the user role who is testing the Action. In order to make the palette 'managed', follow below steps:
        *  Navigate to 'Groups' on the left menu
        *  Find the group you want to manage the Action palette for and click on the selected group
        *  Go to 'Actions' Tab for the selected group
        *  Click on the link to manage Action Palette for different roles
        *  On the Dialog box, select users for whom you want to manage the palette
        *  Click on 'Save'
    *   As soon as total members in the selected group is greater than 5, test Action will not be available for use in that group
*   You can find the test action in the palette of the selected groups and use it accordingly.

# Steps to debug a action

After you have uploaded a test Action, you can debug the html views for the test Action

*   Turn on developer options by tapping on build number 7 times. [Know more](https://www.androidcentral.com/how-enable-developer-settings-android-42).
*   Turn on USB debugging @ Settings -> Developer Options -> USB Debugging
*   Attach phone to computer using USB wire and install the required device drivers if needed . [Know More](https://developer.android.com/studio/run/oem-usb.html)
*   Open Kaizala app and then open the activity which has webview content.
*   Open Chrome browser in computer and type **chrome://inspect** in address bar and hit enter. 
*   User will see his device mentioned there along with an HTML page, which is opened in the webview of his Kaizala app.


**More:** [Instant edit of test Actions](EditAction.md)</br>
**Next:** [Publish to a group](publish.md)
