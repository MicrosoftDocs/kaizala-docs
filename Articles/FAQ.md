# Frequently Asked Questions: 

## Kaizala REST-based APIs

**1. How do I get started using Kaizala APIs?**</br></br>
In order to start using Kaizala's REST-based API, you need to
 
-   First [Set up Kaizala Connector and generate Refresh Token](https://docs.microsoft.com/en-in/kaizala/connectors/setup).
-   Next you need to [generate Access Token](https://docs.microsoft.com/en-in/kaizala/connectors/tokens)
-   and then [start using APIs](https://docs.microsoft.com/en-in/kaizala/connectors/api)

<br/>

**2. How to generate Refresh Tokens programmatically?**</br></br>
  There are two types of Refresh Token.
  - User Token
  - Group Token
  
  **User Token** can be generated using (a) Connectors detail page in Kaizala Management portal, (b) Using API ( GeneratePin and LoginWithPinAndApplicationId api(details in postman collection shared [here](https://app.getpostman.com/run-collection/f68a8abec784cc00b0b9#?env%5BKaizala-APIs-environment%5D=W3siZW5hYmxlZCI6dHJ1ZSwia2V5IjoibW9iaWxlLW51bWJlciIsInZhbHVlIjoiKzkxOTkxMDg3MDAwNSIsInR5cGUiOiJ0ZXh0In0seyJlbmFibGVkIjp0cnVlLCJrZXkiOiJhY2Nlc3MtdG9rZW4iLCJ2YWx1ZSI6IiIsInR5cGUiOiJ0ZXh0In0seyJlbmFibGVkIjp0cnVlLCJrZXkiOiJ0ZXN0LWdyb3VwLWlkIiwidmFsdWUiOiIiLCJ0eXBlIjoidGV4dCJ9LHsiZW5hYmxlZCI6dHJ1ZSwia2V5IjoibW9iaWxlLW51bWJlci0yIiwidmFsdWUiOiIrOTExMTk5OTk5OTk5IiwidHlwZSI6InRleHQifSx7ImVuYWJsZWQiOnRydWUsImtleSI6ImFwaS1yb290IiwidmFsdWUiOiJodHRwczovL2FwaS5rYWl6YS5sYSIsInR5cGUiOiJ0ZXh0In0seyJlbmFibGVkIjp0cnVlLCJrZXkiOiJhcHBsaWNhdGlvbi1pZCIsInZhbHVlIjoiIiwidHlwZSI6InRleHQifSx7ImVuYWJsZWQiOnRydWUsImtleSI6ImFwcGxpY2F0aW9uLXNlY3JldCIsInZhbHVlIjoiIiwidHlwZSI6InRleHQifSx7ImVuYWJsZWQiOnRydWUsImtleSI6ImVuZHBvaW50LXVybCIsInZhbHVlIjoiIiwidHlwZSI6InRleHQifSx7ImVuYWJsZWQiOnRydWUsImtleSI6InJlZnJlc2gtdG9rZW4iLCJ2YWx1ZSI6IiIsInR5cGUiOiJ0ZXh0In0seyJlbmFibGVkIjp0cnVlLCJrZXkiOiJ0ZXN0LXB1YmxpYy1ncm91cC1pZCIsInZhbHVlIjoiIiwidHlwZSI6InRleHQifSx7ImVuYWJsZWQiOnRydWUsImtleSI6InRlc3Qtc3ViLWdyb3VwLWlkIiwidmFsdWUiOiIiLCJ0eXBlIjoidGV4dCJ9LHsiZW5hYmxlZCI6dHJ1ZSwia2V5IjoibW9iaWxlLW51bWJlci0zIiwidmFsdWUiOiIrOTExMDk5OTk5OTkiLCJ0eXBlIjoidGV4dCJ9LHsiZW5hYmxlZCI6dHJ1ZSwia2V5IjoidGVzdC1hY3Rpb24taWQiLCJ2YWx1ZSI6IiIsInR5cGUiOiJ0ZXh0In0seyJlbmFibGVkIjp0cnVlLCJrZXkiOiJ0ZXN0LXN1cnZleS1pZCIsInZhbHVlIjoiIiwidHlwZSI6InRleHQifSx7ImVuYWJsZWQiOnRydWUsImtleSI6InRlc3Qtd2ViaG9vay1pZCIsInZhbHVlIjoiIiwidHlwZSI6InRleHQifV0=) ) (c) Kaizala oAuth. <br/>
  **Group Token** can be generated using Connectors detail page in Kaizala Management portal.

Read more about [Tokens](https://docs.microsoft.com/en-in/kaizala/connectors/tokens)
<br/><br/>

**3. How do I create a group using API?**</br></br>
  Kaizala allows creation of groups & sub-groups using APIs. Read more to [create a group](https://docs.microsoft.com/en-in/kaizala/connectors/groups). 
  >Note: If you are using User Level Refresh Token, new group will be created. But if group level token is used to create a group, a sub-group for the concerned group is created.
<br/><br/>

**4. How can I send a message through APIs in Kaizala?**</br></br>
  Kaizala exposes an API using which you can send a message to any group. Get more details [here](https://docs.microsoft.com/en-gb/kaizala/connectors/messages).
<br/><br/>


**5. Are there sample available online for various Kaizala features like APIs, Webhooks?**</br></br>
  You can find the sample code in C# [here](https://github.com/MicrosoftDocs/kaizala-docs/blob/master/Articles/Samples/Getting%20started%20with%20Kaizala%20REST%20APIs%20-%20C%23%20sample%20(shared).docx)

**6. How can I get the phone numbers of all the members/subscribers in a group?**</br></br>
  Kaizala exposes API to get the details of all the members in a group. Get more details [here](https://docs.microsoft.com/en-gb/kaizala/connectors/members)
  In order to get group member details, you would need to setup the Kaizala Connectors. [Read More](https://github.com/MicrosoftDocs/kaizala-docs/blob/master/Articles/connectors/README.md) 
<br/><br/>


**7. How can we add a member to a group through Kaizala APIs?**</br></br>
  Kaizala exposes API to add members in a group. Get more details [here](https://docs.microsoft.com/en-gb/kaizala/connectors/members).     To make a group member an admin, refer below sample: 
````  
PUT {endpoint-url}/v1/groups/{groupId}/members/{memberId} 

Header: 
accessToken 

Body 
{"role":"Admin"} 
 ````

**8. Is it possible to create a webhook which can notify on group creation?**</br></br>
  It is not possible to create a webhook to get notifications on group creations because all webhooks currently operate within the context of a group. Within the context of a group you can create webhooks to get notifications on messages/actions that are sent/received, member addition and deletion, etc.  
<br/><br/>

**9. Do connectors have to be added manually to every group?**</br></br>
  If the connector is created from Tenant Admin, then you do not have to add the connector manually to every group. 
<br/><br/>


**10. How can I fetch complete responses of all participants in a Survey?**</br></br>
Use the following API to get all the responses for a particular survey in a group:
````
{{endpoint-url}}/v1/groups/{{group-id}}/actions/{{survey-id}}?getDetails=true 
 
Headers: 
accessToken : {{access-token}} 
```` 
<br/><br/>

**11. Can I send a message in a 1-1 conversation in Kaizala through APIs?**</br></br>
  All APIs in Kaizala operate within the context of a group. So it is not possible to send a message in a 1-1 conversation using an API. Following capabilities are supported:
-   Sending message to a particular subscriber in a public group 
-   Creating a group with the user and sending message to the group

<br/>
    
**12. Is it possible to send a message only to particular member in a group?**</br></br>
  Only in the case of a public group it is possible to send a message to particular subscriber. In a normal group this is not possible. Please refer to the following link for more details on the associated API: https://docs.microsoft.com/en-gb/kaizala/connectors/messages. <br/>
<br/><br/>

**13. Is it possible to send a message only to particular member in a group?**</br></br>
  All APIs in Kaizala operate within the context of a group. So it is not possible to send an action in a 1-1 conversation using an API.  
<br/><br/>

## Kaizala Actions

**1. How can I get started with Custom Action Development? Is there any documentation available?**</br></br>
  Custom Action Development and related documentation is still under Preview and is covered under NDA. To get access to Custom Action development guides, please write to us @ KaizalaDev@microsoft.com, along with your GitHub alias and we will provide you access accordingly. 
<br/><br/>

**2. How can I get the latest Kaizala Action SDK?**</br></br>

  Once you have access to the Custom Action Development guide, you can find the latest Action SDK [here](https://github.com/Microsoft/kaizala-docs-preview/blob/master/kaizala/platform/v1/docs/actions/KASClient.zip)
<br/><br/> 

 **3. How can I test/debug a Custom Action without having to upload a package every time?**</br></br>

  To test a custom Action, before it is sent for approval, read more about the steps/process [here](Actions/test.md) 
<br/><br/>


 **4. What are guidelines that Action Package must follow in order to get approved?**</br></br>
While approving a custom Action Package, Microsoft follows guidelines/validations that an Action Package must adhere to. Please find them [here](Actions/validation.md).
<br/><br/>

**5. Where can I access the reports corresponding to my Custom Actions on Kaizala Management Portal?**</br></br>
 Kaizala Management Portal enables users to create custom actions, forms, feedback cards, etc. Such actions can then be mapped to your groups and sent repeatedly to track critical business metrics. On the portal, this data is reported under “Recurrent Survey Reports”. As an additional feature, the report aggregates responses to these cards over time and across instances. 
<br/><br/>

**6. How can I load external content in my action page?**</br></br>
You can load external content in your action by whitelisting the URL which contains the data. You can find steps for URL whitelisting [here](Actions/urlWhitelisting.md).
<br/><br/>

## Integration with Microsoft Apps

**1. How can we create a Kaizala Connector in PowerApps?**</br></br>
  Microsoft Kaizala has been released as a Connector on Microsoft Flow & PowerApps. Read more [here](https://support.office.com/en-us/article/Integrate-your-workflow-in-Kaizala-using-Microsoft-Flow-883343d0-6b16-4725-a23d-bc69fb264356)
<br/><br/>

**2. How can I add and use the Excel Add-in for Kaizala?**</br></br>

  The Excel Add-in for Kaizala allows any table in Excel to be exposed as a Survey on Kaizala. All responses to the Survey will be automatically populated in the Excel table. Read more [here](https://support.office.com/en-us/article/Kaizala-Office-Add-in-4cd01439-5da2-4a9f-b493-8f2e23e2fd91?ui=en-US&rs=en-US&ad=US) 

<br/><br/> 



