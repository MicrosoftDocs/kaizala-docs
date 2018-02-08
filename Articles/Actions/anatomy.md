# Anatomy of a Kaizala Action package

A Kaizala Action package is a regular ZIP file which is not password protected and has a maximum size of 1MB. The resources in the package are at the root of the zip file and not in any directory structure. The resources also cannot reference any external resources other than those present in the package.

The basic components of a Kaizala Action package are 
*   A manifest file in JSON format
*   An app model for your Kaizala Action in JSON format
*   Web resources that constitute your Kaizala Action - HTML, JS, CSS and image files

## Package Manifest

The manifest specifies settings of the Kaizala Action, such as the following:
*   The Action's display name, description, ID, version, and Action icon.
*   Various views that define your Action and mapping them to their respective invokation points
    * A creation view when an Action is invoked from the palette
    * A card view that appears on the chat canvas when an instance of the Action is sent
    * A responder view for users to respond to the Kaizala Action
    * A summary view to view aggregated responses
*   Labels to be used across the native views that encapsulate your custom views

For more information, see [Package Manifest Schema in JSON format](package_manifest_schema.json).

## App Model

The App Model specifies the capabilities of the Kaizala Action including:
*   The data model for the Form object to be used to leverage the Kaizala Aggregation Services
*   Properties for the form object
*   Settings associated with the Form object

For more information, see [App Model Schema in JSON format](https://github.com/MicrosoftDocs/kaizala-docs/blob/master/Articles/Actions/appModel_schema.json).

## Web Resources

As mentioned above, the Kaizala package must include all the resources being referenced inside the package. This includes all the HTML, JavaScript, CSS and image resources.

The most basic Kaizala Action consists of three HTML pages that are displayed when
*   The Kaizal Action is invoked from the Action Palette in the client app - Creation view
*   A user tries to respond to a Action card instance posted on the Chat Canvas in the client app - Response view
*   A user tries to view the summary of all responses posted for a specific Action instace - Summary view

To interact with the Kaizala client app, you can use the [KASClient.js JavaScript API](KASClient/README.md) that we provide.


