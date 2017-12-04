# Frequently Asked Questions: 

  1. **How can we create a Kaizala Connector in PowerApps?**<br/>
  Microsoft Kaizala has been released as a Connector on Microsoft Flow & PowerApps. Read more [here](https://support.office.com/en-us/article/Integrate-your-workflow-in-Kaizala-using-Microsoft-Flow-883343d0-6b16-4725-a23d-bc69fb264356)
<br/><br/>

2. **How can I send a message through APIs in Kaizala?** <br/>
  Kaizala exposes an API using which you can send a message to any group. Get more details [here](https://docs.microsoft.com/en-gb/kaizala/connectors/messages). In order to send messages, you would need to setup the Kaizala Connectors. [Read More](https://github.com/MicrosoftDocs/kaizala-docs/blob/master/Articles/connectors/README.md)
<br/><br/>
3. **How can I get the phone numbers of all the members in a group (subscribers in a public group) through Kaizala APIs?** <br/>
  Kaizala exposes API to get the details of all the members in a group. Get more details [here](https://docs.microsoft.com/en-gb/kaizala/connectors/members)
  In order to get group member details, you would need to setup the Kaizala Connectors. [Read More](https://github.com/MicrosoftDocs/kaizala-docs/blob/master/Articles/connectors/README.md) 
<br/><br/>
 
5. **How can I get started with Custom Action Development? Is there any documentation available?** <br/>
  Custom Action Development and related documentation is still under Preview and is covered under NDA. 
To get access to Custom Action development guides, please write to us @ KaizalaDev@microsoft.com, along with your GitHub alias and we will provide you access accordingly. 
<br/><br/>
6. **How can we add a member to a group through Kaizala APIs? Is it possible to also specify the role for the member, for instance, add an admin user to a group?** <br/>
  Kaizala exposes API to add members in a group. Get more details [here](https://docs.microsoft.com/en-gb/kaizala/connectors/members).     To make a group member an admin, refer below sample: 
````  
    PUT {endpoint-url}/v1/groups/{groupId}/members/{memberId} 
  
    Header: 
    accessToken 

    Body 
    {"role":"Admin"} 
 ````
 
<br/><br/>
7.  **How can I use my own WCF services with Kaizala to bind data (in drop down etc) or send data to my database?** <br/>
  If you are creating Actions through API then you can use your own data, and through Webhook you can even send responses back to your database.  
<br/><br/> 
8.  **Is it possible to create a webhook which can notify on group creation?** <br/>
  It is not possible to create a webhook to get notifications on group creations because all webhooks currently operate within the context of a group. Within the context of a group you can create webhooks to get notifications on messages/actions that are sent/received, member addition and deletion, etc.  
<br/><br/>
9.  **Do connectors have to be added manually to every group?**  <br/>
  If the connector is created from Tenant Admin, then you do not have to add the connector manually to every group. 
<br/><br/>
10. **How can I fetch complete responses of all participants in a Survey?** <br/>
  Use the following API to get all the responses for a particular survey in a group:
````
{{endpoint-url}}/v1/groups/{{group-id}}/actions/{{survey-id}}?getDetails=true 
 
Headers: 
accessToken : {{access-token}} 
```` 
<br/><br/>
11. **How can I test/debug a Custom Action without having to upload a package every time?** <br/>
  To test a custom Action, before it is sent for approval, read more about the steps/process [here](https://github.com/Microsoft/kaizala-docs-preview/blob/master/kaizala/platform/v1/docs/actions/test.md) 

<br/><br/>
12. **How can I add and use the Excel Add-in for Kaizala?** <br/>
  The Excel Add-in for Kaizala allows any table in Excel to be exposed as a Survey on Kaizala. All responses to the Survey will be automatically populated in the Excel table. Read more [here](https://support.office.com/en-us/article/Kaizala-Office-Add-in-4cd01439-5da2-4a9f-b493-8f2e23e2fd91?ui=en-US&rs=en-US&ad=US) 
<br/><br/>
13. **How can I embed the reports generated on Kaizala Management Portal in my website?** <br/>
<br/><br/>
14. **Are there sample available online for various Kaizala features like Webhooks, Custom Actions, Reporting, etc?** <br/>
  Custom Actions is still under preview and access is provided only on request. To get access to Custom Action samples, please write to us @ KaizalaDev@microsoft.com, along with your GitHub alias and we will provide you access accordingly. 
Resources regarding connectors and webhooks can be found [here](https://docs.microsoft.com/kaizala/)
<br/><br/>
15. **Can I send a message in a 1-1 conversation in Kaizala through APIs?** <br/>
  All APIs in Kaizala operate within the context of a group. So it is not possible to send a message in a 1-1 conversation using an API.  
  The following are the capabilities supported: 
  1) Sending message to a particular subscriber in a public group 
  2) Creating a group with the user and sending message to the group 
<br/><br/>
16. **Is it possible to send a message only to particular member in a group?** <br/>
  Only in the case of a public group it is possible to send a message to particular subscriber. In a normal group this is not possible. Please refer to the following link for more details on the associated API: https://docs.microsoft.com/en-gb/kaizala/connectors/messages. <br/>
<br/><br/>
17. **Is there a way to initiate some kind of SSO so that a user logged-in to Kaizala is automatically logged-in to our services? If not, please suggest a mechanism that will suffice this login requirement.** <br/>
<br/><br/> 
 18. **Where can I find info regarding PowerBI and Flow integration with Kaizala?** <br/>
<br/><br/>
 
19. **Is it possible to send a custom action in 1-1 conversation through an API?** <br/>
  All APIs in Kaizala operate within the context of a group. So it is not possible to send an action in a 1-1 conversation using an API.  
<br/><br/>
20. **Where can I access the reports corresponding to my Custom Actions on Kaizala Management Portal?** <br/>
  All your reports can be accessed in the Reports & Analytics section in the Kaizala Management Portal. [Read more](https://support.office.com/en-us/article/Kaizala-Reports-93e22838-5c18-4181-8d12-eca6c0b4019c?ui=en-US&rs=en-US&ad=US)
<br/><br/>

