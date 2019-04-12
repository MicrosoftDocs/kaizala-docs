# Drive performance using Leaderboard
A leaderboard is a rich visual representation of participants to provide an understanding of where they rank in comparison to peers. Leveraging the power of gamification, leaderboards are the best way to instill competitive spirit among teams and also track individual/team performance against business targets. They provide instant feedback to course-correct and identify patterns in KPIs that could help employees improvise.

This generic solution is a great way to incentivize team and create an open culture. It can be used by any sales or service organization to track performance- Individual or Team and compare performance across multiple KPIs. 

Excel from your Onedrive for Business is consumed by Microsoft Flow and Leaderboard card is sent to Kaizala group in a recurrence pattern. This card has two views- Chat card view & Immersive view. 

Chat card view 

<img src="Leaderboard/2.JPG" width="200">


Immersive view

This view has two tabs, first being a wall of fame for Top 10 performers, second is "My performance" which is different for each user.
<img src="Leaderboard/1.PNG" width="200">

My Performance has 2 sections that display my statistics and nearby ranks. 

<img src="Leaderboard/11.PNG" width="200">


## Implementation steps
This can be broadly divided into 3 steps:
1. Upload Action Package
2. Format Excel Sheet
3. Configure Microsoft Flow

### Upload Action package
1. Download the “Leaderboard-SolutionPackage.zip”(*This* *contains* *"Leaderboard_ActionPackage.zip"* *and* *"Leaderboard_FlowPackage.zip"* *Package*)[PlaceholderforGithubLink]
2. Download the latest version of Kaizala ["ActionSDK.Zip"](https://manage.kaiza.la/MiniApps/DownloadSDK) (*This contains KASClient.js*)
3. Edit "Leaderboard_ActionPackage.zip"
   1. Unzip "Leaderboard_ActionPackage.zip" to a folder
   2. Change the action "id" and "provider name" in package.json
   3. Add KASClient.js to this folder 
   4. Zip all the contents in this folder (*This folder is your modified action package which should be imported to Kaizala Management Portal*)
   5. [Import](https://docs.microsoft.com/en-us/kaizala/actions/publish#import-kaizala-action) the edited action package to [Kaizala Management Portal](https://manage.kaiza.la/)(*This card is sent by calling an API, so no need to add the card to a group*)

### Format Excel Sheet

1.Download the [Excel template](Github link)

2. Fill all mandatory fields -Name, PhoneNo, and Score. Apart from these three mandatory fields, the rest are KPIs (optional) and are displayed in "My Performance" tab.

    <img src="Leaderboard/3.JPG" width="600">

     > Note: Score & KPIs can be numeric or % values. If the column has percentages, apply [percent number](https://support.office.com/en-ie/article/format-numbers-as-percentages-de49167b-d603-4450-bcaa-31fba6c7b6b4) format to that column

     > Note: My Performance tab can have a maximum of 6 KPIs


3. [Rename](https://support.office.com/en-us/article/rename-an-excel-table-fbf49a4f-82a3-43eb-8ba2-44d21233b114) excel table as "Leaderboardyyyymmdd" E.g, Leaderboard20190431 for the day 2019/04/31(yy/mm/dd)

4. Save this file in One Drive for Business

      > Note: Flow automatically picks up the excel data of that day based on the table name and sends the card.

### Configure Microsoft Flow

1. [Import](https://flow.microsoft.com/en-us/blog/import-export-bap-packages/) the "Leaderboard_FlowPackage.zip"[LinktoGithub] to your Microsoft Flow account

      > Note- If you have never used Sharepoint or Kaizala connections, first [add connections](https://docs.microsoft.com/en-us/flow/add-manage-connections)    

2. Edit details in Imported Flow (*See steps below*)

    1. In the second block, enter the card title in the value field, that you want to show in the leaderboard. For E.g, "Sales Leaderboard" 

         <img src="Leaderboard/4.JPG" width="600">
    
    2. In the third block, set value as  true if the "score" is a percentage, if not set it to false
         <img src="Leaderboard/6.JPG" width="600">

    3. In the seventh block

       1. Select Location as "OneDrive for Business" from the dropdown

       2. Select Document library as "OneDrive" from the dropdown

       3. Select Excel file on clicking folder picker
     
             > Note: Table name that you have given in excel file will be automatically picked up by the flow. 
       
             <img src="Leaderboard/7.JPG" width="600">


    4. In the ninth block, "Apply to each", 

        1. Edit KPI labels in Parse JSON block for E.g, KPI 1 as Deals closed & KPI 2 as Calls converted.

             <img src="Leaderboard/8.JPG" width="600">

             >Note: Card can display a maximum of 6 KPI's 

        2. Edit KPI labels in Compose (*as shown below*)
        
             <img src="Leaderboard/9.PNG" width="600">

        
    5. In the last block

        1. Enter the group ID or select group name where you want to send the card

        2. Click on Action to select "Action package" from drop down
        
        3. Click on Action package to select "enter a custom value" and enter your "action package id" that you have given package.json

        4. Save the Flow

           <img src="Leaderboard/10.JPG" width="600">

Leaderboard card will be sent to the specified group as per the interval and frequency set in the Flow. 

>Note: If you wish to change the labels- "Name", "PhoneNo" and "Score" in excel sheet, change it to desired labels in Immersive.js

```
      
 "/*Fields from excel */

const NAME = "Name";
const PHONENO = "PhoneNo";
const SCORE = "Score";"      

