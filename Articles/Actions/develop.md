# Developing a new Kaizala Action

A Kaizala Action package is a zip file which contains all the requried manifest and resource files at the root.

To begin with, create a new folder on your PC to make it your working dorectory.

You will need a code editor to work with different kinds of web resources & manifest files.

>   We recommend the Visual Studio Code editor. You can download it from [here](https://code.visualstudio.com/)

## Defining the App Model

The Kaizala Actions currently support form based data models that can be used for creating, collecting and aggregating data using the Kaizala Aggregation Services.

So, you will first need to define the ‘questions’ you need to include to create a form object.

Refer to the [app Model JSON Schema](appModel_schema.md) to create your Action's app model.

## Define the Creation View

When a new instance of the Kaizala Action is invoked from the app's Action Palette, the HTML resource marked as the CreationView is rendered. The objective of this creation view is to 
create a new instance of the Form object as defined in the app model. 

To interact with the Kaizala Aggregation Services and creating the new form instance, you can refer to the APIs in the [KASClient JS SDK](KASClient/README.md). You will need to 
download the [KASClient JS File](https://manage.kaiza.la/MiniApps/DownloadSDK) and include it in your package.

Create a new HTML file that represents this creation view. In the corresponding javascript file, invoke the KASClient JS SDK and create a form object.

## Create the Package Manifest file

Now that you have a semblance of what you want to achieve and have successfully created a view – you can start creating your package manifest file.

The Kaizala Package manifest file provides essential information for the Kaizala platform for it to recognize and run your custom Kaizala action.

Refer to the [package manifest JSON Schema](package_manifest_schema.md) to create your Action's package manifest.

At this point, you should also include an icon file for your custom Action in the package.

Refer to your creation view HTML file in the package manifest and map it to the relevant parameter object.

## Configure the card that appears on the conversation canvas

When a new instance of a Kaizala Action is created and posted in a conversation, an Action Card is displayed on the canvas for other users in the conversation to view and submit their responses.

In order to customize the Chat Card View, please refer to [Customizing ChatCardView](ChatCanvasCardView.md) 
## Define the Response & Summary Views

When users try to view details and respond to an instance of the Kaizala Action posted in a conversation, they can see two types of views.
*   Response view when they tap on the primary call-to-action button and want to post a reponse
*   Summary view when they tap on the card header and would like to view the aggregated view of all the reesponses posted

Create one or more HTML files as required for you to define your Action and map them to the relevent parameters in the package manifest file.

To interact with the Kaizala Aggregation Services and the Kaizala Native client to retrieve information, submit a response or get aggregated responses, you can refer to the APIs in the [KASClient JS SDK](KASClient/README.md).


## Create the ZIP file

Select all the files in your working directory and create a new zip file for your package. Ensure that all files are present in the root directory of the package.

*   Next: [Publish](publish.md)
