# Display internal announcements made on SharePoint announcement list in Kaizala groups 
Organizations use SharePoint Announcement List to share news, statuses and other short bits of information to employees . Announcement List is a special type of list that lets you create an announcement with an expiry date.

Using this sample, Organizations can share SharePoint announcements with the first line and mobile workers on Kaizala.

The chat card view (*as below*)

![Chat card view logo](https://www.fnordware.com/superpng/pnggrad16rgb.png)

Immersive view (*as below*)

![Immersive view logo](https://www.fnordware.com/superpng/pnggrad16rgb.png)

This scenario can be broadly divided into 2 steps:

	1. Create an announcement list with Columns- Title, Announcement Body (description) and Attachments
	
	Note- Rich text is not supported by out of box announcement card. Switch off rich text for column that has Announcement body(description)
	
	2. Configure Flow such that, when a new item is created or existing item is modified in SharePoint list, Announcement is sent to a group

![Sharepoint+ Flow--> Kaizala](https://www.fnordware.com/superpng/pnggrad16rgb.png)

## Implementation steps-

	1. Download the solution package (This contains Flow Package)
	2. [Add Announcement app to SharePoint site](https://docs.microsoft.com/en-us/sharepoint/administration/add-apps-for-sharepoint-to-a-sharepoint-site)
		○ Click on the settings icon
		○ Click on Add an App 
		○ Select Announcement App from the list of available Apps
	Use the [highlighted content web part](https://support.office.com/en-us/article/use-the-highlighted-content-web-part-e34199b0-ff1a-47fb-8f4d-dbcaed329efd) (*if necessary ,for visualization*)
	3. [Import Flow Package](https://flow.microsoft.com/en-us/blog/import-export-bap-packages/)
	4. Edit the Flow (*Steps as Below*)

		○ In the First block of the Flow
			§ Enter the site address
			§ Enter the List name

		Steps to get List name

			§ Click on site contents tab on the left hand corner of the screen
			§ Select the announcement list from which you want to send announcements to Kaizala
			§ Click on gear icon at the top right corner of the screen
			§ Go to List settings
			§ Copy the URL of the list
			§ Decode the URL (you can decode the URL [here](https://www.url-encode-decode.com/) )
    
![Flow block 1--> Kaizala](https://www.fnordware.com/superpng/pnggrad16rgb.png)

		○ In the second block of the Flow
			§ Map "value" field with column that has description of announcement (Column title in the SharePoint announcement list) from Dynamic content. In the below example, the column name is "Announcement Body"
        
![Flow Column Map--> Kaizala](https://www.fnordware.com/superpng/pnggrad16rgb.png)

        ○ In the Last block of the Flow
			§ Select the group name or Map the group ID where you want to send the card 

![last block Map--> Kaizala](https://www.fnordware.com/superpng/pnggrad16rgb.png)

	5. Save the flow

Announcement will be sent to the selected Kaizala group, each time flow is triggered by.

**Note**- Text File is not supported as attachment


