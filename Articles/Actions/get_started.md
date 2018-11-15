# Get Started with custom Kaizala Actions

## Kaizala Action Development Lifecycle

The typical development lifecycle of a Kaizala Action includes the following steps:

  **Step 1 - Decide on the purpose of the Kaizala Action**
    
    Ask the following questions:
    
      - How is the Action useful? 
      - How does it make sense in a conversational context?
      - What is the information that flows from the creator to a responder and vice versa?
      - What scenarios does your Action support?
    
Decide the most important features and scenarios and focus your design around them.

   **Step 2 - Identify the data model for the Kaizala Action**

All Kaizala Actions are currently Form based - i.e. the data model for requesting, collecting and aggregating information is a set of question and answer types that are supported by the Kaizala Aggregation Services (KAS) platform. Think of how the data required for your action can levergage the form infrastructure to work effectively.

   **Step 3 - Design and implement the user experience and user interface for the add-in.**

Design a fast and fluid user experience that is consistent, easy to learn, with primary scenarios that require only a few steps to complete. Remember that a Kaizala Action cannot refer to external sources - so be practical in terms of what you would like to implement within your Action.

You can choose from a variety of web development tools and use HTML and JavaScript to implement the user interface.

You can use the KAS Client JS SDK to interact with the Kaizala Aggregation Services and the native Kaizala Client. 

   **Step 4 -Create a manifest file for the Action based on the Package Manifest Schema**

Create a manifest file in JSON notation to identify the Action and its components and specify the names of the view files.

**Step 5 - Create a ZIP file of the package and upload it on the portal**

Create a ZIP file of the package with all of it's resources at the root of the package.

Upload the package on the Kaizala Management Portal. After upload, Action is in Draft state

**Step 6 - Stage the Draft Action**

On the detail page of the Action version which is in draft state, Tap on 'Stage' button. Once an Action is staged, you can test & debug the Action 

 **Step 7 - Activate the Staged Action**

Once an Action is in staged state, and has been tested successfully, you can activate the Action in your organization. Action moves to Active state. Other members in your organization can also add this Action to their respective groups.

  **Step 8 - Add the Action to respective groups**

Once Action is in Active state, you can deploy the Action to groups associated with your organization. 

