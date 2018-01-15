# Get Started with custom Kaizala Actions

## Kaizala Action Development Lifecycle

The typical development lifecycle of a Kaizala Action includes the following steps:

1.  **Decide on the purpose of the Kaizala Action**
    
    Ask the following questions:
    
      - How is the Action useful? 
      - How does it make sense in a conversational context?
      - What is the information that flows from the creator to a responder and vice versa?
      - What scenarios does your Action support?
    
Decide the most important features and scenarios and focus your design around them.

2.  **Identify the data model for the Kaizala Action**

All Kaizala Actions are currently Form based - i.e. the data model for requesting, collecting and aggregating information is a set of question and answer types that are supported by the Kaizala Aggregation Services (KAS) platform. Think of how the data required for your action can levergage the form infrastructure to work effectively.

3.  **Design and implement the user experience and user interface for the add-in.**

Design a fast and fluid user experience that is consistent, easy to learn, with primary scenarios that require only a few steps to complete. Remeber that a Kaizala Action cannot refer to external sources - so be practical in terms of what you would like to implement within your Action.

You can choose from a variety of web development tools and use HTML and JavaScript to implement the user interface.

You can use the KAS Client JS SDK to interact with the Kaizala Aggregation Services and the native Kaizala Client. 

4.  **Create a manifest file for the Action based on the Package Manifest Schema**

Create a manifest file in JSON notation to identify the Action and its components and specify the names of the view files.

5.  **Create a ZIP file of the package and upload it on the portal**

Create a ZIP file of the package with all of it's resources at the root of the package.

Upload the package on the Kaizala Management Portal.

6.  **Submit the Action for Approval**

Submit the Action for approval by the Kaizala team. 

7.  **Publish the Action to respective groups or your tenancy**

Once approved, you can deploy the Action to groups or tenancy associated with your organization. 

