## KAS Client

KAS Client SDK provides a bridge between the Kaizala app's native interface (Objective-C for iOS, Java for Android) and your Kaizala Action's javascript.

Broadly KASClient APIs are divided into two categories:
1.  **Form APIs**: Each Action's conversation card is associated with a form object. A form defines the behaviour of the Action. To create an Action instance you need to initialize 
a form object, put necessary information in it, and then submit it as a request to the respective conversation. Participants in the conversation can respond to the form, 
or see the aggregated summary of all the responses. These APIs were created to deal with everything related to forms. Based on different flows, these can further be 
sub-categorized into:
    *   **Creation flow APIs**:  Tapping on the Action's icon in palette launches its creation flow. Using these APIs you can initialize a form object, manipulate it, and submit it as a request.
	*   **Response flow APIs**: Tapping on the respond button of a Action card launches its response flow. Using these APIs you can get the associated form object, all the previous responses, and submit a new response.
	*   **Summary flow APIs**: Tapping on the summary button of a Action card launches its summary flow. Using these APIs you can get the associated form object, all the aggregated responses by the participants, and choose to close the form so that further responses are not allowed.
    
2.  **App APIs**: These are APIs that can be used to interact with the Kaizala client's native interface and retrieve necessary information. This includes generic APIs, like show contact-picker, image-picker, get current device location, app locale, etc. These APIs can be used in any of the flows mentioned above.

You can download the current KASClient Javascript file from [here](../../../js/KASClient.js)

## API Reference

*	[Form creation flow APIs](form_creation.md)
*	[Form response flow APIs](form_response.md)
*	[Form Summary flow APIs](form_summary.md)
*	[App APIs](generated/modules/kasclient.app.md)

## Object Reference

References of all the objects in the SDK are avaialable [here](objects.md).