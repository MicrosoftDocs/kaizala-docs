# Display SharePoint Announcements in Kaizala groups 
Organizations use SharePoint Announcement app to share news, status and other short bits of information to employees . Sharepoint Announcement app, that comes with a list, is a special type of list that lets you create an announcement with an expiry date.

Using this sample, Organizations can share SharePoint announcements with the first line and mobile workers on Kaizala. This card has 3 fields in chat card view- Attachments( In this example, Photo story of images), Title and Announcemnet body (description). This is sent to kaizala group as an out-of-box announcement card.

The chat card view is as below

<img src="/Articles/Business%20Solutions/Corporate%20communications/Sample%20Solutions/SharepointAnnouncementsonKaizala/Sharepoint%20announcement%20Images/1.png" alt="Chat card view Logo" width="340" />

On tapping the card, the immersive view is as below

<img src="/Articles/Business%20Solutions/Corporate%20communications/Sample%20Solutions/SharepointAnnouncementsonKaizala/Sharepoint%20announcement%20Images/2.png" alt="immersive view Logo" width="180" />

This scenario can be broadly divided into 2 steps:

1.  Create an announcement list with Columns- Title, attachments and announcemnet body(description)
	
> Note- Rich text is not supported by out-of- box announcement card. Switch off rich text for sharepoint column that has Announcement body(description) while creating that column.
	
2. Configure Flow such that, when a new item is created or existing item is modified in announcement list, an out-of-box announcement card is sent to a Kaizala group

<img src="/Articles/Business%20Solutions/Corporate%20communications/Sample%20Solutions/SharepointAnnouncementsonKaizala/Sharepoint%20announcement%20Images/3.png" alt="Sharepoint&Flow Logo" width="500" />

## Implementation steps-

1. Download the ["SharepointAnnouncemnetOnkaizala-SolutionPackage.zip"](/Articles/Business%20Solutions/Corporate%20communications/Sample%20Solutions/SharepointAnnouncementsonKaizala/SharepointAnnouncementOnKaizala-SolutionPackage.zip) (*This is a Flow package*)
2. [Add "Announcement app" to SharePoint site](https://docs.microsoft.com/en-us/sharepoint/administration/add-apps-for-sharepoint-to-a-sharepoint-site)(*steps as below*)
     - Click on the settings icon
     - Click on Add an App 
     - Select Announcement App from the list of available Apps
3. Use the [highlighted content web part](https://support.office.com/en-us/article/use-the-highlighted-content-web-part-e34199b0-ff1a-47fb-8f4d-dbcaed329efd) (*if necessary ,for visualization*)
4. [Import downloaded Flow Package to your Microsoft Flow account](https://flow.microsoft.com/en-us/blog/import-export-bap-packages/)

> Note- If you have never used Sharepoint or Kaizala connection, first [add connections](https://docs.microsoft.com/en-us/flow/add-manage-connections)

5. Edit the Flow (*Steps as Below*)

     - In the First block of the Flow
	     - Enter the site address
	     - Enter the List name
            
	    Steps to get List name
                 
		 - Click on site contents tab on the left hand corner of the screen
		 - Select the announcement list from which you want to send announcements to Kaizala
		 - Click on settings icon at the top right corner of the screen
		 -  Go to List settings
		  -  Copy the URL of the list from the browser.
		  -  Decode the URL (you can decode the URL [here](https://www.url-encode-decode.com/) )
    
          <img src="/Articles/Business%20Solutions/Corporate%20communications/Sample%20Solutions/SharepointAnnouncementsonKaizala/Sharepoint%20announcement%20Images/4.png" alt="" width="500" />

	- In the second block of the Flow
	   - Map "value" field with column that has description of announcement (Select column title in the SharePoint announcement list) from Dynamic content. In the below example, the column title is "Announcement Body"
        
       <img src="/Articles/Business%20Solutions/Corporate%20communications/Sample%20Solutions/SharepointAnnouncementsonKaizala/Sharepoint%20announcement%20Images/5.png" alt="" width="600" />

     - In the Last block of the Flow
	    -  Select the group name from dropdown or Map the group ID where you want to send the card
       <img src="/Articles/Business%20Solutions/Corporate%20communications/Sample%20Solutions/SharepointAnnouncementsonKaizala/Sharepoint%20announcement%20Images/6.png" alt="" width="450" />
       
      - To get the group id, go to your group on https://manage.kaiza.la and select the identifier at the end of the URL.
        <img src="/Articles/Business%20Solutions/Corporate%20communications/Sample%20Solutions/GetRSSFeedsonKaizala/GetRSSFeedsOnKaizalaImages/6.PNG" alt="" width="450" />     
      
 

6. Save the flow

Announcement will be sent to the selected Kaizala group, each time flow is triggered.

> Note- Text File is not supported as attachment


