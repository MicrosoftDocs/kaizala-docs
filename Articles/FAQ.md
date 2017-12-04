# Frequently Asked Questions: 

<ol>
<li>
** How can we create a Kaizala Connector in PowerApps?**<br/>
 Microsoft Kaizala has been released as a Connector on Microsoft Flow & PowerApps. Read more [here](https://support.office.com/en-us/article/Integrate-your-workflow-in-Kaizala-using-Microsoft-Flow-883343d0-6b16-4725-a23d-bc69fb264356)

</li> 
<li>How can I send a message through APIs in Kaizala? <br/>
Kaizala exposes a connector using which you can send a message to any group. Please follow the below link to get the complete details: 
https://docs.microsoft.com/en-gb/kaizala/connectors/messages 
Before you get started, please refer to Setup for using the Kaizala Connectors 
</li> <li>
How can I get the phone numbers of all the members in a group through Kaizala APIs? <br/>
Kaizala exposes a connector using which you can get the details of all the members in a group. Please follow the below link to get the complete details: 
https://docs.microsoft.com/en-gb/kaizala/connectors/members 
Before you get started, please refer to Setup for using the Kaizala Connectors 
</li> <li>
How can I get the phone numbers of all the subscribers in a public group through Kaizala APIs? <br/>
Kaizala exposes a connector using which you can get the details of all the members in a group. Please follow the below link to get the complete details: 
https://docs.microsoft.com/en-gb/kaizala/connectors/members 
Before you get started, please refer to Setup for using the Kaizala Connectors 
</li> <li>
 
How can I get started with Custom Action Development? Is there any documentation available? <br/>
Custom Action Development and related documentation is still under Preview and is covered under NDA. 
To get access to Custom Action development guides, please write to us with your GitHub user name and we will provide you access. 
</li> <li>
How can we add a member to a group through Kaizala APIs? Is it possible to also specify the role for the member, for instance, add an admin user to a group? <br/>
Kaizala exposes a connector using which you can add members in a group. Please follow the below link to get the complete details: 
https://docs.microsoft.com/en-gb/kaizala/connectors/members 
Before you get started, please refer to Setup for using the Kaizala Connectors 
To make a group member an admin, refer below sample: 
PUT {endpoint-url}/v1/groups/{groupId}/members/{memberId} 
  
Header: 
accessToken 
 
Body 
{"role":"Admin"} 
 
 </li> <li>
How can I use my own WCF services with Kaizala to bind data (in drop down etc) or send data to my database? <br/>
If you are creating Actions through API then you can use your own data, and through Webhook you can even send responses back to your database.  
</li> <li> 
Is it possible to create a webhook which can notify on group creation? <br/>
It is not possible to create a webhook to get notifications on group creations because all webhooks currently operate within the context of a group. Within the context of a group you can create webhooks to get notifications on messages/actions that are sent/received, member addition and deletion, etc.  
</li> <li> 
Do connectors have to be added manually to every group?  <br/>
If the connector is created from Tenant Admin, then you do not have to add the connector manually to every group. 
</li> <li>
How can I fetch complete responses of all participants in a Survey? <br/>
Use the following API to get all the responses for a particular survey in a group: 
{{endpoint-url}}/v1/groups/{{group-id}}/actions/{{survey-id}}?getDetails=true 
 
Headers: 
accessToken : {{access-token}} 
 
</li> <li> 
How can I test/debug a Custom Action without having to upload a package every time? <br/>
To deploy a Custom Action that is under development, include the following parameters to your Custom Action’s package.json 
 
“dials” : { 
“forTesting”:true 
} 
With the forTesting flag set to true, the custom action can be pushed to any group with less than five members. This flag also bypasses the Approval workflow for actions. Please ensure that the Managed Palette setting is enabled. Only then this new action will be visible in the palette. 
On an Android device, you can use chrome://inspect in your Chrome Browser to debug the contents loaded in the webviews.  
</li> <li> 
How can I add and use the Excel Add-in for Kaizala? <br/>
The Excel Add-in for Kaizala allows any table in Excel to be exposed as a Survey on Kaizala. All responses to the Survey will be automatically populated in the Excel table.  
The Excel Add-in for Kaizala can be found in the Add-ins store of Office 365. Install the Add-in. Create a table in Excel and provide headers for the table. The table headers will be exposed as questions on Kaizala. Select the table and click on Share on Kaizala button in the Kaizala Add-in. You will be prompted to login with your Kaizala registered phone number. Once you log in, a list of your groups will be available from which you can select a group to which you want to send this survey. 
</li> <li>
How can I embed the reports generated on Kaizala Management Portal in my website? <br/>
</li> <li>
Are there sample available online for various Kaizala features like Webhooks, Custom Actions, Reporting, etc? <br/>
Custom Actions is still under preview and access is provided only on request. Please write to us with your GitHub user name and we will provide access. 
Resources regarding connectors and webhooks can be found here:  
https://docs.microsoft.com/kaizala/ 
</li> <li>
Can I send a message in a 1-1 conversation in Kaizala through APIs? <br/>
All APIs in Kaizala operate within the context of a group. So it is not possible to send a message in a 1-1 conversation using an API.  
The following are the capabilities supported: 
1) Sending message to a particular subscriber in a public group 
2) Creating a group with the user and sending message to the group 
</li> <li>
Is it possible to send a message only to particular member in a group? <br/>
Only in the case of a public group it is possible to send a message to particular subscriber. In a normal group this is not possible. Please refer to the following link for more details on the associated API: https://docs.microsoft.com/en-gb/kaizala/connectors/messages. <br/>
</li> <li>
Is there a way to initiate some kind of SSO so that a user logged-in to Kaizala is automatically logged-in to our services? If not, please suggest a mechanism that will suffice this login requirement. <br/>
</li> <li> 
Where can I find info regarding PowerBI and Flow integration with Kaizala? <br/>
</li> <li>
 
Is it possible to send a custom action in 1-1 conversation through an API? <br/>
All APIs in Kaizala operate within the context of a group. So it is not possible to send an action in a 1-1 conversation using an API.  
</li> <li>
Where can I access the reports corresponding to my Custom Actions on Kaizala Management Portal? <br/>

All your reports can be accessed in the Reports & Analytics section in the Kaizala Management Portal. 
</li>
