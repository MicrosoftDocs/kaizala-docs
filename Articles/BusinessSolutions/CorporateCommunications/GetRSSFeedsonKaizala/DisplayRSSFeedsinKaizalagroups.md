# Display RSS feeds in Kaizala groups

Organizations use RSS feeds to complement their e-mail systems and improve the way they provide information to employees. Organizations can now leverage these feeds with the first line and mobile workers by sending them as announcements to Kaizala groups.

Few use cases of RSS feeds:

1. Industry News from external sites
2. Company news from internal sites
3. Compete Information from external sites
4. Product Updates
5. Group specific feeds, E.g., Finance, Design and Tech 
6. Tips and Tricks, E.g, DIY, Sports and Photography

This sample will help, an admin user to add RSS feeds to Kaizala groups. This card has 3 fields in chat card view- Card title(E.g., Business News), Image and Feed title. Tapping on the card would take the user to web view within Kaizala. 
 
 >Note: Only whitelisted RSS feed URL's open within Kaizala, if not, the content would be directed to a browser.

<img src="GetRSSFeedsOnKaizalaImages/1.png" alt="Chat card view Logo" width="400" />

This is an announcement in the form of a card and Flow is used to send this custom action card to Kaizala group.

<img src="GetRSSFeedsOnKaizalaImages/2.png" width="450" />

## Implementation steps

1. Download the ["GetRSSFeedsOnKaizala-SolutionPackage.zip"](https://aka.ms/GetRssFeedsonKaizala-SolutionPackage.zip) (*This package contain "RSS-feed-ActionPackage.zip" and "RSS-feed-FlowPackage.zip"*)
2. Download the latest version of Kaizala ["ActionSDK.Zip"](https://manage.kaiza.la/MiniApps/DownloadSDK)(*This contains KASClient.js file*)
3. Edit the "RSS-feed-ActionPackage.zip" (*as below*)
   1. Unzip action package "RSS-feed-ActionPackage.zip" to a folder
   2. Change the action "id" and "provider name" in package.json
   3. Add KASClient.js file to this folder 
   4. Add RSS feed URL in package.json(as below) to whitelist that URL. In this example, digital trends URL is whitelisted.    
         ```
      "externalUrls": [
      { "url": "https://www.digitaltrends.com" }
      ]  
      ```
   5. Zip all the contents in this folder (*This folder is your modified Action package which should be imported to kaizala management portal*)
   
 > Note: Select all the files in your working directory and create a new zip file for your package. Ensure that all files are present in the root directory of the package. This should include KASClient.js, package.json with new "id", "provider name" and whitelisted URL
 
4. [Import](/kaizala/actions/publish#import-kaizala-action) the edited action package to kaizala management portal (*This card is sent by calling API, so there is no need to add the card to a group*)
5. [Import](https://flow.microsoft.com/en-us/blog/import-export-bap-packages/) the "RSS-feed-Flowpackage.zip" to your Microsoft Flow account

    > Note: If you have never used RSS or Kaizala connections, first [add connections](/flow/add-manage-connections)	

6. Edit details in Imported Flow (*See steps below*) 
   1. In the first block , enter the RSS feed URL
       <img src= "GetRSSFeedsOnKaizalaImages/3.1.PNG" width="600" />
   2. In the second block, enter the card title in "value" field. The card title will be visible to users in chat card view. E.g., "Business News"
   
      <img src= "GetRSSFeedsOnKaizalaImages/3.2.PNG" width="600" />
   3. In the third block, enter the Action "id" in "value" field, that you have given in package.json
      <img src="GetRSSFeedsOnKaizalaImages/4.png" width="600" />
   4. In the last block of the Flow
        1. Select the group name or enter the group id where you want to send the card
        2. To get the group id, go to your group on https://manage.kaiza.la and select the identifier at the end of the URL.
        
            <img src="GetRSSFeedsOnKaizalaImages/6.PNG" width="600" />
            
        3. Click on action, to select action type as "custom value" from the dropdown
        4. Map body to "ActionBodyJson"
       
       <img src="GetRSSFeedsOnKaizalaImages/5.png" width="600" />
7.  Save the Flow

 RSS feeds will be sent to the selected Kaizala group, each time flow is triggered. 

> Note: You can only set one RSS feed URL in the Flow. To direct multiple feeds to same group, different Flows have to be created for each feed

> Known issue: On iOS, the ads take the user out of the webview since they are not whitelisted

### Useful links
1. [How to create Kaizala Groups](/office365/kaizala/groups)
2. [Configure RSS Feed to SharePoint site](https://support.office.com/article/create-or-subscribe-to-an-rss-feed-fb35047d-8dbd-412a-a5f3-f1712af14dcb)
