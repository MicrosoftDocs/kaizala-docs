# Auto-Post Twitter updates to Kaizala

Posting to Twitter employee pages is part of daily business, but having to post the same information multiple times is quite difficult. Encouraging employees to share social media updates, when done properly can dramatically expand company's following. 

This sample solution saves your time by auto-posting Tweets from your official Twitter account to Kaizala groups. An announcement card is sent to the group when one or all the below triggers occur

1. A new tweet is posted on a specific Twitter handle E.g.,"@InsideFabrikam"

2. A post is re-tweeted in that Twitter handle 
	
3. A post has a specific hashtag E.g.,"#EmployeeEngagement"

<img src="AutoPostTwitterUpdatesToKaizalaImages/6.png" alt="Tweet" width="400" />

This card has three fields- card title, attachments(images, videos or GIF) and body (description). The announcement body has the Twitter URL and on tapping this URL, users would be directed to status page on Twitter.

> Note: In case of Video or GIF, thumbnail is shown in chat card view

Chat card View:

<img src="AutoPostTwitterUpdatesToKaizalaImages/1.png" alt="Chat card view Logo" width="400" />

Immersive View:

<img src="AutoPostTwitterUpdatesToKaizalaImages/2.png" alt="Immersive view Logo" width="190" />

In this scenario, Flow is used to send the card to a selected group in Kaizala.

<img src="AutoPostTwitterUpdatesToKaizalaImages/3.png" alt="Flow+Twitter>Kaizala" width="500" />

## Implementation steps:

1. Download the [AutoPostTwitterUpdatesToKaizala-SolutionPackage.zip](https://aka.ms/AutoPostTwitterUpdatesToKaizala-SolutionPackage.zip) (*This contains Flow Package*)

2. [Import](https://flow.microsoft.com/en-us/blog/import-export-bap-packages/) the "AutoPostTwitterUpdatesToKaizala-SolutionPackage.zip" to your Microsoft Flow account

     > Note- If you have never used Twitter or Kaizala connections, first [add connections](/flow/add-manage-connections)

3. Edit the Flow (*as Below*)

    1.  In the first block of the Flow
    
	    Enter the Twitter handle or enter the hashtag, or both
		
	    <img src="AutoPostTwitterUpdatesToKaizalaImages/4.PNG" alt="Firstblock>Kaizala" width="400" />
	
    2.  In the last block of the Flow
      
	    1. Select the group name 
	
	    2. Enter the title. The title will be visible to users in chat card view. E.g., "InsideFabrikam"
	 
	    <img src="AutoPostTwitterUpdatesToKaizalaImages/5.PNG" alt="Flow+Twitter>Kaizala" width="400" />
	 
4. Save the flow

Announcement will be sent to the selected Kaizala group, each time Flow is triggered.

> Note:In case of tweets with polls/location only the poll question/tweet text will show up in the card, not the poll options or the tweet location

> Note: Please check with your IT admin in case of any [DLP policy](/flow/prevent-data-loss) set by your organization for Twitter
