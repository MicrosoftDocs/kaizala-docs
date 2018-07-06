# Instant Edit of Actions in Staged environment

Before you start editing Actions, please enable [Staged state](test.md)

While creating a Action, the HTML views and its associated files (css, js) are bundled within the Action package and is imported on the Kaizala Management Portal. Any further modifications to the views require the package to be recreated and uploaded on the Kaizala Management Portal.

In order to simplify the subsequent editing of the HTML views, Kaizala enables edit of HTML, JavaScript and CSS files locally and instantly see the updates in the Kaizala App. This involves creating a local HTTP server which will host the updated files and Kaizala App will use those files, instead of the files present in the actual package.

>  **Note:** In order to enable instant edit, Action must be uploaded on Kaizala Management Portal and should be in staged state

## Enable Instant Edit in Android devices

### Steps to create local HTTP server in Windows

* **Step 1: Create a copy of Action Package in your local Machine**

  * Create a copy of the Action package in a location of your choice on your machine. The name of the folder should be the Action Id.
    
* **Step 2: Run python command**

  *  Open command Terminal and navigate to the folder containing the Action Package.
  *  Run this command: `python -m SimpleHTTPServer 8000`
  
      > Installation of Python is a pre-requisite to run the above script.
  
* **Step 3: Check local server**

  * Your local server URL will now be `http://localhost/<ActionId>:8000`
  * To check your server open a browser and enter above local server url in the address bar and you should be able to see the contents of the folder from which the server was started.
  
### Steps to setup your Android device

> Pre-Requisite: You need to enable debug mode, as mentioned [here](test.md). Approved versions of Actions do not support this feature

* **Step 1: Connect your Machine to device via a usb**

	* Your device must be connected to the your machine via usb
	
* **Step 2: Enable Diagnostics on Kaizala App**	

	* In Kaizala, go to Profile -> Settings -> About. Tap on 'Microsoft Kaziala logo' five times to enable Diagnostics option. *		* Press Back to reach Settings page. Click on 'Troubleshoot' option under 'Diagnostics' label at the bottom of the Settings page
	* Turn on the 'Mini Apps Location Override' switch to enable the Server URL field.
	* Go to <chrome://inspect/> on your host machine and enable port forwarding. In port forwarding settings, give the port number as "8000"(first tab) and IP address and port as "localhost:8000" (second tab)
	* With this change Kaizala will fetch the HTML/css/JS files of your Action from the server instead of using the packaged files
	
* **Step 3: Make changes in the Action folder of your machine**

	* Any modifications to the files can be observed immediately by reloading the view in the app (navigate away from the view and opening it again)
	
Once the editing process is complete the updated files can be bundled to create the package and update the package present in the portal. Turn off the Mini App Location Override switch in the Diagnostics page to restore default behavior.

