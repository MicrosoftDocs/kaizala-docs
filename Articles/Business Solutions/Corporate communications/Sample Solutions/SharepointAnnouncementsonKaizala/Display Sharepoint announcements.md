# Display SharePoint Announcements in Kaizala groups 
Organizations use SharePoint Announcement app to share news, status and other short bits of information to employees . Sharepoint Announcement app, that comes with a list, is a special type of list that lets you create an announcement with an expiry date.

Using this sample, Organizations can share SharePoint announcements with the first line and mobile workers on Kaizala. This card has 3 fields in chat card view- Attachments( In this example, Photo story of images), Title and Announcement body (description). This is sent to kaizala group as an out-of-box announcement card.

The chat card view is as below

<img src="/Articles/Business%20Solutions/Corporate%20communications/Sample%20Solutions/SharepointAnnouncementsonKaizala/Sharepoint%20announcement%20Images/1.png" alt="Chat card view Logo" width="340" />

On tapping the card, immersive view is as below

<img src="/Articles/Business%20Solutions/Corporate%20communications/Sample%20Solutions/SharepointAnnouncementsonKaizala/Sharepoint%20announcement%20Images/2.png" alt="immersive view Logo" width="180" />

This scenario can be broadly divided into 2 steps:

1. Create an announcement list with Columns- Title, attachments and announcement body(description)
	
> Note- Rich text is not supported by out-of-box announcement card. Switch off rich text for sharepoint column that has Announcement body(description) while creating that column.
	
2. Configure Flow such that, when a new item is created or existing item is modified in announcement list, an out-of-box announcement card is sent to a Kaizala group

<img src="/Articles/Business%20Solutions/Corporate%20communications/Sample%20Solutions/SharepointAnnouncementsonKaizala/Sharepoint%20announcement%20Images/3.png" alt="Sharepoint&Flow Logo" width="500" />

## Implementation steps


1. [Add Announcement app](https://docs.microsoft.com/en-us/sharepoint/administration/add-apps-for-sharepoint-to-a-sharepoint-site) to SharePoint site(*as below*)
     1. Click on the settings icon
     2.  Click on Add an App 
     3.  Select Announcement App from the list of available Apps
2. Use the [highlighted content web part](https://support.office.com/en-us/article/use-the-highlighted-content-web-part-e34199b0-ff1a-47fb-8f4d-dbcaed329efd) (*if necessary , for visualization*)
3. Download the [SharepointAnnouncementOnkaizala-SolutionPackage.zip](/Articles/Business%20Solutions/Corporate%20communications/Sample%20Solutions/SharepointAnnouncementsonKaizala/SharepointAnnouncementOnKaizala-SolutionPackage.zip) (*This is a Flow package*)
4. [Import](https://flow.microsoft.com/en-us/blog/import-export-bap-packages/) SharepointAnnouncementOnkaizala-SolutionPackage.zip to your Microsoft Flow account

> Note: If you have never used Sharepoint or Kaizala connection, first [add connections](https://docs.microsoft.com/en-us/flow/add-manage-connections)

5. Edit the Flow (*as below*)

    1. In the First block of the Flow
	     1. Enter the site address
	     2. Enter the List name
            
	    Steps to get List name
		 1.  Click on site contents tab on the left hand corner of the screen
		 2.  Select the announcement list from which you want to send announcements to Kaizala
		 3. Click on settings icon at the top right corner of the screen
		 4.  Go to List settings
		 5.  Copy the URL of the list from the browser.
		 6. Decode the URL (you can decode the URL [here](https://www.url-encode-decode.com/) )
    
         <img src="/Articles/Business%20Solutions/Corporate%20communications/Sample%20Solutions/SharepointAnnouncementsonKaizala/Sharepoint%20announcement%20Images/4.png" alt="" width="500" />

   2. In the second block of the Flow
	  
	  Map "value" field with column title of announcement list, that has announcement body(description) from Dynamic content. In the below example, the column title is "Announcement Body"
        
       <img src="/Articles/Business%20Solutions/Corporate%20communications/Sample%20Solutions/SharepointAnnouncementsonKaizala/Sharepoint%20announcement%20Images/5.png" alt="" width="600" />

    3. In the Last block of the Flow
       
       Select the group name from dropdown. In this Example it is "Everyone@Fabrikam"
       
       <img src="/Articles/Business%20Solutions/Corporate%20communications/Sample%20Solutions/SharepointAnnouncementsonKaizala/Sharepoint%20announcement%20Images/6.png" alt="" width="450" />

6. Save the flow

Announcement will be sent to the selected Kaizala group, each time flow is triggered.

> Note: Text File is not supported as attachment
