# Test and Debug

Once Custom Action development is done, you may want to test it to see if its working fine end to end and fix any bugs that you discover in testing. As well as in some cases, you would like to debug the html views for any possible issues.

The Kaizala Management Portal provides a convenient way to test & debug your new Kaizala Actions. 
>   You will need an active Kaizala Pro or Office365 Organizational subscription to access the Management Portal.

## Steps to test a Action

After you have satisfied the pre-requisites, you can test your action by following below steps

* 	Navigate to the Kaizala Management Portal @ https://manage.kaiza.la/
*    Log in using an existing Office365 account
*    Register a phone number on the portal by tapping on “Add a Phone Number”
*    Tap on "Actions" on the left menu
*    Select 'My Actions' from the dropdown
*    Find and click on the Action that you want to test 
*    Open the version of the Action that is in draft state
*    On this page, Tap on 'Stage'
*    Once the Action is staged, you can add the Action to the groups which you are an Admin of

> The group must have a managed palette for the user role who is testing the Action

In order to make the palette 'managed', follow below steps:
*    Navigate to 'Groups' on the left menu
*    Find the group you want to manage the Action palette for and click on the selected group
*    Go to 'Actions' Tab for the selected group
*    Click on the link to manage Action Palette for different roles
     *    On the Dialog box, select users for whom you want to manage the palette
     *    Click on 'Save'
*    You can find the action in the palette of the selected groups and use it accordingly.

## Steps to debug a action

After you have uploaded a test Action, you can debug the html views for the test Action

*   Turn on developer options by tapping on build number 7 times. [Know more](https://www.androidcentral.com/how-enable-developer-settings-android-42).
*   Turn on USB debugging @ Settings -> Developer Options -> USB Debugging
*   Attach phone to computer using USB wire and install the required device drivers if needed . [Know More](https://developer.android.com/studio/run/oem-usb.html)
*   Open Kaizala app and then open the activity which has webview content.
*   Open Chrome browser in computer and type **chrome://inspect** in address bar and hit enter. 
*   User will see his device mentioned there along with an HTML page, which is opened in the webview of his Kaizala app.


**More:** [Instant edit of Staged Actions](EditAction.md)</br>
**Next:** [Publish to a group](publish.md)
