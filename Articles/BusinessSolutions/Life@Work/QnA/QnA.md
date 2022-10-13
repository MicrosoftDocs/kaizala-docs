# Get structured answers to your questions from co-workers

Elevating employee engagement is essential for the success of any organization-whether it’s a small startup or large corporation that operates across multiple locations. It can be challenging for leaders and managers to know how employees are feeling about company policies, projects, jobs, and assigned tasks.

With the increase in mobile workforce conducting such QnA sessions with managers, on the go, can be even more difficult. On resorting to QnA session on mobile chat, the replies to questions can interrupt the flow and end-user may miss out on information

With QnA card, users can ask questions to managers and rest of the community view all the replies in a structured format.

This is a simple card with a creation view, that allows the user to submit a question, a chart card view for users to see the latest comment and a summary view that allows users to view and participate in the discussion.

Creation view:

<img src="QnAImages/1.png" alt="Chat card view Logo" width="200" />

Chat card View:

<img src="QnAImages/2.png" alt="Chat card view Logo" width="200" />

Summary View:

<img src="QnAImages/3.png" alt="Chat card view Logo" width="200" />

## Implementation Steps:
1. Download the ["QnA-SolutionPackage.zip"](https://aka.ms/QnA-SolutionPackage) (*This contains action package*)
2. Download the latest version of Kaizala ["ActionSDK.Zip"](https://manage.kaiza.la/MiniApps/DownloadSDK) (*This contains KASClient.js*)
3. Edit the "QnA-SolutionPackage.Zip" (*as below*)
   1. Unzip "QnA-SolutionPackage.Zip" to a folder
   2. Change the Action "id" and "providerName" in package.json
   3. Add KASClient.js to this folder (*rename the KASClient(1).js to KASClient.js if required*)
   4. Zip all the contents in this folder (*This folder is your modified action package which should be imported to kaizala management portal*)    
       
      > Note: Select all the files in your working directory and create a new zip file for your package. Ensure that all files are present in the root directory of the package. This should include  KASClient.js, package.json with new action "id" and "providerName".
       
4. [Import](/kaizala/actions/publish#import-kaizala-action) the edited action package to [kaizala management portal](https://manage.kaiza.la/)
5. [Publish](/kaizala/actions/publish) the action and add the action to a group where you want to add the card
6. Select user roles as admin and member to publish the card in the flat group

> Note: This card works only in Flat group. All the group members and admins can create and send this card in a flat group.
