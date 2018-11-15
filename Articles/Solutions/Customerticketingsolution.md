# Customer ticketing solution on Kaizala
![](Images/Customer%20ticketing%20solution.PNG)
<br>
<br> In this, let us explore on how to get a customer support ticket management system on Kaizala. Instead of sending multiple text messages to give an update on the ticket status, we could just have a rich card that provides the ticket status. And, when there is a change in status, the card could be updated to reflect the latest status.
<br><br>To achieve this, below are the steps that would be required:
<br>1. Build a card with custom chat card based on defined properties
<br>2. Call into an API to send the card ( scenario where ticket is raised )
<br>3. Call into an API to update the card ( scenario where ticket status changes )
## Building card with custom chat card view
[Kaizala allows to extend client side functionality using custom actions / cards. Microsoft documentation for developing a custom action can be found [here](https://github.com/MicrosoftDocs/kaizala-docs/blob/master/Articles/Actions/develop.md).]
<br><br>For building a card with custom chat card, we will need to define the sourceLocation of the chat canvas card view in package.json. Unlike the Response view, creation view or results / summary view – which are html / JS based, the chat card takes a declarative schema [more about it [here](https://github.com/MicrosoftDocs/kaizala-docs/blob/master/Articles/Actions/ChatCanvasCardView.md)].
### package.json
{
 <br>"id": "com.gls.xyz.care",
 <br>"schemaVersion": 1,
 <br>"displayName": "Customer Support",
 <br>"providerName": "GLS-Test",
 <br>"icon": "AppIcon.png",
 <br>"version": "1",
 <br>"minorVersion": "1",
 <br>"appModel": "AppModel.json",
 <br>"description": "Package for sending customer ticket [test]",
 <br>"dials": {
 <br>"isLocalised": false,
 <br>"isPinned": false
 <br>},
 <br>"views": {
 <br>"ChatCanvasCardView": {
 <br>"sourceLocation": "ChatCardView.json",
 <br>"showReceipts": true,
 <br>"showLikes": false,
 <br>"showComments": false,
 <br>"showExpiry": false,
 <br>"showFooter": true,
 <br>"showHeader": false,
 <br>"showFooter": false,
 <br>"isResponseEditable": false
 <br>}
<br> }
<br>}
### ChatCardView.json
The chat card here has four fields: one hard-coded to “XYZ CUSTOMER CARE” and the other 3 fields fed from properties: customername, ticketnumber and ticketstatus.
<br>{
<br> "schemaVersion":2,
 <br>"schema":{
<br> "type":"container",
<br> "initialHeight":300,
<br> "layout":"vertical",
<br> "children":[
<br> {
 <br>"type":"text",
 <br>"paddingLeft":10,
 <br>"paddingRight":10,
<br> "paddingTop":10,
<br> "paddingBottom":10,
<br> "string":"XYZ CUSTOMER CARE",
<br> "fontSize":18,
<br> "fontStyle":"bold",
<br> "textColor":"#ffffff",
<br> "backgroundColor":"#fcb72d",
<br> "textAlignment":"center",
<br> "maxNumberOfLines":1,
<br> "marginBottom":10
<br> },
<br> {
<br> "type":"text",
<br> "paddingLeft":10,
<br> "paddingRight":10,
<br> "string":"${Form.properties[customername].value}",
<br> "fontSize":18,
<br> "fontStyle":"regular",
<br> "textColor":"#000000",
<br> "backgroundColor":"#ffffff",
<br> "textAlignment":"left",
<br> "maxNumberOfLines":5,
<br> "marginBottom":10
<br> },
<br> {
<br> "type":"text",
<br> "paddingLeft":10,
<br> "paddingRight":10,
<br> "string":"${Form.properties[ticketnumber].value}",
<br> "fontSize":18,
<br> "fontStyle":"regular",
<br> "textColor":"#000000",
<br> "backgroundColor":"#ffffff",
<br> "textAlignment":"left",
<br> "maxNumberOfLines":2,
<br> "marginBottom":10
<br> },
<br> {
<br> "type":"text",
<br> "paddingLeft":10,
<br> "paddingRight":10,
<br> "string":"${Form.properties[ticketstatus].value}",
<br> "fontSize":18,
<br> "fontStyle":"regular",
<br> "textColor":"#000000",
<br> "backgroundColor":"#ffffff",
<br> "textAlignment":"left",
<br> "maxNumberOfLines":2,
<br> "marginBottom":10
<br> }
<br> ]
<br> }
<br>}
### AppModel.json
Just create an AppModel with the title and empty questions array.
<br> {
<br> "title": "XYZ Customer Support",
<br> "questions": []
<br>}
## Sending ticket from API
To send the ticket via API, we would be using the actions endpoint as shown below. Notice the subscribers array – since we need to send this targeted to the particular subscriber ( for more information, you can refer the post [Move SMS notifications to Kaizala](https://kaizala007.wordpress.com/2018/02/07/kaizala-subscriber-message/)).
<br>Executing this API would give you the referenceId and actionId. Cache this actionId as we will need it in the next step. In the below example, we have set the customername, ticketnumber and ticketstatus properties to “NAME: John Thomas”,  “TICKET#: 907050”, “STATUS: ACTIVE” respectively.

| Method  |      POST    |
|----------|-------------|
|**URL**|{{endpoint-url}}/v1/groups/{{test-group-id}}/actions|
|**Request Body**|{<br>id:”com.gls.xyz.care”,<br>subscribers:[“{{subscriber-mobile-number}}”],<br>sendToAllSubscribers:false,<br>actionBody:{<br>properties:[<br>{<br>name:”customername”,<br>value:”NAME: John Thomas”,<br>type:”Text”<br>},<br>{<br>name:”ticketnumber”,<br>value:”TICKET#: 907050″,<br>type:”Text”<br>},<br>{<br>name:”ticketstatus”,<br>value:”STATUS: ACTIVE”,<br>type:”Text”<br>}<br>]<br>}<br>}|
## Updating the ticket status using API
As the ticket status changes, we would need to update the status on the card that was sent. For that we would be using the actions/<<action-id>>/properties endpoint. In the below example, we would be updating the ticket status to RESOLVED. Notice that the actionId is the ID of the action sent in the earlier step.

| Method  |      PPUT    |
|----------|-------------|
|**URL**|{{endpoint-url}}/v1/groups/{{test-group-id}}/actions/{{actionId}}|
|**Request Body**|{<br>{<br>“version”:-1,<br>“updateProperties”:<br>[<br>{<br>“name” : “ticketstatus”,<br>“type” : “Text”,<br>“value” : “STATUS: RESOLVED”<br>}<br>]<br>}|

## Screenshots of the demo
### Ticket sent from API
![](Images/Ticket%20sent%20from%20API.PNG)
### Ticket after updating the status from API
![](Images/Ticket%20after%20updating%20the%20status%20from%20API.PNG)
<br>Sharing the package at [here](https://drive.google.com/file/d/1gQb1CpYVd8SLnOOH4PCZWPsUeYhdWehB/view), in case you want to give it a shot. ( don’t forget to change the package id before uploading to Kaizala to prevent conflicts )

















