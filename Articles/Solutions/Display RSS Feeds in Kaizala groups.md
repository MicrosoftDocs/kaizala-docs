# Display RSS feeds in Kaizala groups

Organizations use RSS feeds to complement their e-mail systems and improve the way they provide information to employees. Organizations can now leverage these feeds with the first line and mobile workers by sending them as announcements to Kaizala groups.

Five use cases of RSS feeds

1. Industry News from external sites
2. Company news from internal sites
3. Compete Information from external sites
4. Product Updates
5. Group specific feeds, Ex- Finance, Design and Tech 
6. Tips and Tricks, Ex- DIY, Sports and Photography

This sample will help, an admin user to add RSS feeds to Kaizala groups.  This card has 3 fields in chat card view- Card title(Ex- Business News), Image, Feed title ( Title of the News Feed). Tapping on the card will take you to web view within Kaizala. 
 
 >Note: Only whitelisted RSS feed URL's open within kaizala, if not, the content would be directed to a browser.

<img src="./Images/RSS%20Feed%20Images/1.png" alt="Chat card view Logo" width="400" />

This is an announcement in the form of a card and Microsoft Flow is used to send this custom action card to Kaizala group.

<img src="./Images/RSS%20Feed%20Images/2.png" alt="RSS+Flow--> Kaizala logo" width="450" />

## Implementation steps

1. [Download the "RSS-feed-SolutionPackage.zip"](https://github.com/MicrosoftDocs/kaizala-docs/blob/master/Articles/Solutions/Sample%20Solutions/Rss-Feed-solutionPackage.zip) (*This package contain "RSS-feed-ActionPackage.zip" and "RSS-feed-FlowPackage.zip"*)
2. [Download the latest version of Kaizala "ActionSDK.Zip"](https://manage.kaiza.la/MiniApps/DownloadSDK)(*This contains KAS client file*)
3. Edit the "RSS-feed-ActionPackage.zip" (*See steps below*)
   - Unzip action package "RSS-feed-ActionPackage.zip" to a folder
   - Change the action "id" and "provider name" in package.json (*this step is mandatory*)
   - Add KAS client file to this folder 

> Note - To whitelist RSS feed URL, add that URL in Package.json (as below). In this example, "www.digitaltrends.com" is the external URL. 

``` json
"externalUrls": [
    { "url": "https://www.digitaltrends.com" }
  ]	
} 
```
 - Zip all the contents in this folder (*This folder is your new Action package*)
 
> Note - Select all the files in your working directory and create a new zip file for your package. Ensure that all files are present in the root directory of the package. This should include KAS client, package.Json with new "id", "provider name" and whitelisted URL
	
4. [Import the edited action package to kaizala management portal](https://docs.microsoft.com/en-us/kaizala/actions/publish#import-kaizala-action) (*This card is sent by calling API, so there is no need to add the card to a group*)
5. [Import the "RSS-feed-flowpackage.zip" to your Microsoft Flow account](https://flow.microsoft.com/en-us/blog/import-export-bap-packages/)

> Note- If you have never used RSS or Kaizala connections first [add connections](https://docs.microsoft.com/en-us/flow/add-manage-connections)
	
6. Edit details in Imported Flow (*See steps below*) 
   - In the First block , enter the RSS feed URL
   - In the second block, enter the card title in "value" field. The card title will be visible to users in chat card view. Ex- "Business News"

   <img src="./Images/RSS%20Feed%20Images/3.png" alt="Flow 1 & 2 blocks--> Kaizala logo" width="600" />

   - In the third block, enter the Action "Id" in "value" field, that you have given in Package.json
   
   <img src="./Images/RSS%20Feed%20Images/4.png" alt="Flow 1 & 2 blocks--> Kaizala logo" width="600" />
   
   - In the Last block of the Flow, Select the group name or enter the group id where you want to send the card

   <img src="./Images/RSS%20Feed%20Images/5.png" alt="Flow 1 & 2 blocks--> Kaizala logo" width="600" />

   - To get the group id, go to your group on https://manage.kaiza.la and select the identifier at the end of the URL.

   <img src="./Images/RSS%20Feed%20Images/6.PNG" alt="Flow 1 & 2 blocks--> Kaizala logo" width="600" />

7.  Save the Flow

RSS feeds will be sent to the selected Kaizala group, each time flow is triggered by RSS Updates. 



> Note: You can only set one RSS feed URL in the Flow. To direct multiple feeds to same group, different Flows have to be created for each feed

> Known issue: On iOS, the ads take the user out of the webview since they are not whitelisted

### Useful links

1. [How to create Kaizala Groups](https://docs.microsoft.com/en-us/office365/kaizala/groups)
2. [Configure RSS Feed to SharePoint site](https://support.office.com/en-us/article/create-or-subscribe-to-an-rss-feed-fb35047d-8dbd-412a-a5f3-f1712af14dcb)
