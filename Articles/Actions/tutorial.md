# Practice Tutorial: Creating a new Kaizala Action 

## Overview 
In this tutorial, we will create a custom Kaizala Action utilizing the extensible Action framework provided by the Kaizala platform.

We will create an “Ask Feedback” Action which will allow Kaizala users to ask for feedback from other users in terms of 1-to-5 star ratings on questions asked – along with any comments they would like to provide.  

You can download sample Kaizala Action packages from [here](https://manage.kaiza.la/MiniApps/DownloadSDK).

## Pre-requisites 
* A smartphone (Android/iOS) with Kaizala app installed 
* An Office365 Account 
* Access to an HTML/JS editor (notepad/Visual Studio Code/etc.) 

## Steps to create a sample Action

*   **Step 1:** Create a new directory for your Action package  
    * Create a new directory on your desktop & name it “SampleAction” 
    * Place all the subsequent files in this directory

*   **Step 2:** Define a data model for your Action 
    * First, we need to define the data model which will be used in our custom Action 
    * The Kaizala Actions are currently form based data models. So, we will first need to define the ‘questions’ we need to include in our form. 
    * Since this is a “Ask Feedback” action – we will plan to use two pieces of data 
        * Numeric rating (value 1 to 5) 
        * Comment/Verbatim feedback if any  

    *   Kaizala Forms infrastructure supports below question types:

        | Question Type | Description |
        | :---: | :---: | 
        | SingleSelect | Single choice question with options |
        | MultiSelect | Multiple choice question with options | 
        | Text | Question with a plain text answer |
        | Numeric | Question with a numeric answer | 
        | Location | Question with a location answer | 
        | DateTime | Question with DateTime answer | 
        | Image | Question with a picture as an answer | 
    

    * For our two questions we will use Question Type of 'Numeric' & 'Text' for Rating number & comments respectively 
        * Create a new file called “appModel.json” and place the following content in the file. The file contains the two questions listed in order 
        `````
        { 
            "questions": [{ 
                    "title": "Rating", 
                    "type": "Numeric" 
                }, 
                { 
                    "title": "Comments", 
                    "type": "Text" 
                } 
            ], 
            "title": "Ask Feedback", 
            "visibility": "All", 
            "isAnonymous": false, 
            "isResponseAppended": false 
        } 
        `````
        * Note: Above code also contains additional metadata we will learn about later (out of scope for this session) 
        * Save the file
        
*   **Step 3:** Define a view for creating the request for feedback  
    *   We will now create a new HTML file which will be used to create new instances of  our Kaizala Action 
    *   This is the view that is invoked when the icon is tapped from the palette. In this view, we would like to ask them what they would like feedback on. 
    * Create a new file called “CreationView.html” and place the below HTML in the file 
        `````
        <html> 
         
        <head> 
        </head> 
         
        <body onload="onCreatePageLoad()"> 
            <br/> <br/> 
            <div> 
                <p>What would you like feedback on?</p> 
                <br/> <br/> 
                <input type="text" name="description" id="description" placeholder="Enter question text here" value=""> 
            </div> 
            <br/> <br/> 
            <div> 
                <input type="submit" name="submit" value="Submit" onclick="submitData()"> 
            </div> 
        </body> 
         
        </html> 
        `````
    *   Save the file 
*   **Step 4:** Include the Kaizala Forms JS SDK 
    * To make it easy for developers to leverage the Forms Infrastructure, Kaizala provides a JavaScript wrapper library that you can include in your custom Actions 
    * Download the file below & place it in the same directory as your datamodel.json and CreationView.html 
      *   [Kaizala Forms JS SDK ](https://manage.kaiza.la/MiniApps/downloadSDK). [Read more](KASClient/README.md)
 
 
 
 
*   **Step 5:** Use the Kaizala Forms JS SDK to submit form   
    * Add the following code snippet in the <head> element of your “CreationView.html” to refer to the Kaizala Forms JS SDK 
        `````
        <head> 
            <script type="text/javascript" src="KASClient.js"></script> 
        </head> 
        `````
    * Now, when the user clicks submit, we need to verify that he has entered a question to ask feedback on – and create the Form Instance  
    * We also need to instantiate the form on page load. Add the following JavaScript snippet to your “CreationView.html” inside the <head> element 
        `````
            <script type="text/javascript"> 
                var _form; // type: KASForm
         
                // Below will be called on onload of CreationView.html 
                function onCreatePageLoad() { 
                    KASClient.Form.initFormAsync (function (form, error) { 
                        if (error != null) { 
                            showAlert("Error:initFormAsync:" + error); 
                            return; 
                        } 
                        _form = form; 
                    }); 
                } 
         
                function submitData() {
                    var description = document.getElementById("description").value; 
                    if (description == null || description == "") { 
                        KASClient.App.showNativeErrorMessage("Please enter the details for what you would like feedback on."); 
                    } else { 
                        // Set the description to form title 
                        _form.title = description; 
         
                        // Finally send the request 
                        KASClient.Form.submitFormRequest(_form); 
                    } 
                } 
            </script>
        `````

    *   Save the file

*   **Step 6:** Create the Action package manifest   
    *   Now that we have a semblance of what we want to achieve and successfully created a view – we will now create the package manifest file that refers to these files. 
    * Package manifest file provides essential information for the Kaizala platform for it to recognize and run your custom Kaizala action. 
    * We will create a package manifest and specify the following things: 
        * Display name for your Kaizala Action 
        * Custom Id for the Action 
        * Mapping of the creation view to our CreationView.html page 

    * Before that we will need an icon for the Action package. Download the [icon file](https://github.com/MicrosoftDocs/kaizala-docs/blob/main/Articles/Actions/icon.png) & save it as icon.png in the same folder as the other files.

    * Create a new file called “package.json” and add following snippet to the file. Ensure that you edit the id to make your Action unique/distinct 
        `````
        { 
            "id": "com.microsoft.mobile.kaizala.swads.FeedbackSample", 
            "schemaVersion": 1, 
            "version": 1,
            "minorVersion": 1,
            "providerName": "Microsoft Inc.", 
            "displayName": "Ask Feedback", 
            "description": "Custom action to collect feedback.", 
            "icon": "icon.png", 
            "appModel": "appModel.json", 
            "views": { 
                "CreationView": { 
                    "labelHeader": "Feedback requested", 
                    "sourceLocation": "CreationView.html" 
                } 
            } 
        }
        `````
    * You can configure the card that appears on Kaizala chat canvas by specifying the strings in the package manifest.  
    * Modify the “Views” object in you package manifest to match the below snippet:
        `````
        "views": { 
                    "CreationView": { 
                        "labelHeader": "Feedback requested", 
                        "sourceLocation": "CreationView.html"            
                    }, 
                    "ChatCanvasCardView": { 
                        "labelResponded": "You have provided feedback.", 
                        "labelRespondToForm": "PROVIDE FEEDBACK", 
                        "isResponseEditable": true 
                    } 
        }   
        `````
    * Save the file

*   **Step 7:** Create the response view   
    * Now we will create the view that appears to Kaizala users responding to an instance of our action 
    * Create a new file call ResponseView.html and insert the below snippet in the file 
    * We will do the following 
        * Add radio button selection for the rating 
        * Prepare a form response object and code to submit the form 
        ````` 
            <html> 
             
            <head> 
                <title></title> 
                <script type="text/javascript" src="KASClient.js"></script> 
                <script> 
                    var _form; // type: KASForm
                    var _myFormResponses; // type: KASFormResponse[]
             
                    // Below will be called on onload of ResponseView.html 
                    function onResponsePageLoad() { 
                        KASClient.Form.getFormAsync(function (form, error) { 
                            if (error != null) { 
                                KASClient.App.showNativeErrorMessage("Error:getFormAsync:" + error); 
                                return; 
                            } 
                            _form = form; 
                            
                            // Document title would be the form title
                            document.getElementById("title").innerHTML = _form.title;
                            
                            KASClient.Form.getMyFormResponsesAsync(function (responses, error) { 
                                if (error != null) { 
                                    KASClient.App.showNativeErrorMessage("Error:getMyFormResponsesAsync:" + error); 
                                    return; 
                                } 
                                _myFormResponses = responses;
                                
                                // Render previous response, if any
                                if (isCurrentUserResponded()) {
                                    var rating = _myFormResponses[0].questionToAnswerMap["0"];
                                    var remark = _myFormResponses[0].questionToAnswerMap["1"];

                                    var options = document.getElementsByName('option');
                                    options[rating - 1].checked = true;

                                    document.getElementById("description").value = remark;
                                    document.getElementById("description").placeholder = "";
                                }
                            }); 
                        }); 
                    } 
             
                    function submitData() { 
                        var selectedOption = getSelectedOption(); 
                        var remark = document.getElementById("description").value; 
                        submitFormResponse(selectedOption, remark); 
                    } 
             
                    function getSelectedOption() { 
                        // Check which radio button is checked 
                        var options = document.getElementsByName('option'); 
                        for (var i = 0; i < options.length; i++) { 
                            if (options[i].checked) { 
                                return parseInt(options[i].value); 
                            } 
                        } 
                    } 
             
                    // Below will be called when responder submits a new response 
                    function submitFormResponse(selectedOption, remark) { 
                        if (remark == null || remark == "") { 
                            KASClient.App.showNativeErrorMessage("Please fill remark"); 
                        } else if (selectedOption == "") { 
                            KASClient.App.showNativeErrorMessage("Please select one option"); 
                        } else { 
                            // For submitting response a question-answer 
                            // map is required, lets create that! 
                            var questionToAnswerMap = JSON.parse("{}"); 
                            questionToAnswerMap[0] = selectedOption; 
                            questionToAnswerMap[1] = remark; 
             
                            var responseId = null; 
                            var isEditingPreviousResponse = false;
                            
                            // If there is a previous response, update it
                            if (isCurrentUserResponded()) {
                                responseId = _myFormResponses[0].id;
                                isEditingPreviousResponse = true;
                            }
             
                            // Finally submit the response 
                            KASClient.Form.sumbitFormResponse(questionToAnswerMap, responseId, isEditingPreviousResponse); 
                        } 
                    }
                    
                    function isCurrentUserResponded() {
                        return _myFormResponses && _myFormResponses.length > 0;
                    }
                </script> 
            </head> 
             
            <body onload="onResponsePageLoad()"> 
                <br/> <br/> 
                <div> 
                    <p id="title"></p> 
                </div> 
                <div> 
                    <br/> <br/> 
                    <div> 
                        <p>Select your rating:</p> 
                        <br/> <br/> 
                        <div> 
                            <label>1</label> 
                            <input type="radio" name="option" id="option0" value="1" checked> 
                        </div> 
                        <div> 
                            <label>2</label> 
                            <input type="radio" name="option" id="option1" value="2"> 
                        </div> 
                        <div> 
                            <label>3</label> 
                            <input type="radio" name="option" id="option2" value="3"> 
                        </div> 
                        <div> 
                            <label>4</label> 
                            <input type="radio" name="option" id="option3" value="4"> 
                        </div> 
                        <div> 
                            <label>5</label> 
                            <input type="radio" name="option" id="option4" value="5"> 
                        </div> 
                    </div> 
                    <br/> <br/> 
                    <div> 
                        <p>Comments</p> 
                        <input type="text" name="description" id="description" placeholder="Please enter your comments here."> 
                    </div> 
                    <br/> <br/> 
                </div> 
                <div class="footer"> 
                    <input type="submit" name="submit" value="Submit" onclick="submitData()"> 
                </div> 
            </body> 
             
            </html> 
            `````
*   **Step 8:** Create the summary view   
    * Now we will create the view that appears to Kaizala users viewing the summary of the action 
    * Create a new file call SummaryView.html and insert the below snippet in the file. This will create a summary view of the total ratings and comments

            <html> 
             
            <head> 
                <title></title> 
                <script type="text/javascript" src="KASClient.js"></script> 
                <script type="text/javascript"> 
                    // Globals 
                    var _form; // type: KASForm 
                    var _myFormResponses; // type: KASFormResponse[]
                    var _formSummary; // type: KASFormFlatSummary 
                    var _users; // type: Dictionary<UserId: KASUser>
             
                    // Below will be called on onload of SummaryView.html 
                    function onSummaryPageLoad() {            
                        KASClient.Form.getFormAsync(function (form, error) {                
                           if (error != null) {                    
                              KASClient.App.showNativeErrorMessage("Error:getFormAsync:" + error);                    
                              return;                
                           }                
                           _form = form;
                           KASClient.App.showProgressBar("Fetching summary");
                           KASClient.Form.getFormSummaryAsync(
                              function (flatSummary, processedSummary, error) { // In this callback data is fetched from local database
                                 if (error != null) {                    
                                    KASClient.App.showNativeErrorMessage("Error:getFormSummaryAsync:callback1:" + error);                    
                                    return;                
                                 } 
                                 onGetSummary(flatSummary);
                              },
                              function (flatSummary, processedSummary, error) { // In this callback data is fetched from server
                                 KASClient.App.hideProgressBar();
                                 if (error != null) {                    
                                    KASClient.App.showNativeErrorMessage("Error:getFormSummaryAsync:callback2:" + error);                    
                                    return;                
                                 }
                                 onGetSummary(flatSummary);
                              }
                           );           
                        });        
                     }

                     function onGetSummary(summary) {
                        _formSummary = summary;                    
                        KASClient.App.getUsersDetailsAsync(_formSummary.getRespondedUserIds(), function (users,
                           error) {                        
                           if (error != null) {                            
                              KASClient.App.showNativeErrorMessage("Error:getUsersDetailsAsync:" + error);                            
                              return;                        
                           }                        
                           _users = users;  // Document title would be the form title 
                           
                           document.getElementById("title").innerHTML = _form.title; 
                           
                           // Get all responses of the user, and find the average
                           var totalRating = 0;                        
                           var responseCount = 0;          
                           for (var userId in _users) {
                              var userResponses = _formSummary.getResponsesForUserId(userId); // type: Dictionary<QuestionId, string[]>
                              totalRating += parseInt(userResponses["0"][0]);                            
                              responseCount += 1;                       
                           } 
                           
                           document.getElementById("avg").innerHTML = totalRating / responseCount;                    
                        });
                     }
                </script> 
            </head> 
             
            <body onload="onSummaryPageLoad()"> 
                <div class="header"> 
                    <p id="title">Title</p> 
                    <br/> <br/> 
                    <p id="rating">Average Rating: </p> 
                    <p id="avg">avg</p> 
                </div> 
            </body> 
             
            </html>

    

    * Edit the Views object in your package manifest to the following: 
        `````
           "views": { 
                    "CreationView": { 
                        "labelHeader": "Feedback requested", 
                        "sourceLocation": "CreationView.html"            
                    }, 
                    "ChatCanvasCardView": {
                        "labelResponded": "You have provided feedback.", 
                        "labelRespondToForm": "PROVIDE FEEDBACK", 
                        "isResponseEditable": true 
                    }, 
                    "ResponseView": { 
                        "labelHeader": "Provide feedback",
                        "sourceLocation": "ResponseView.html" 
                    }, 
                    "ResponseResultsView": { 
                        "labelPageHeader": "Feedback summary",
                        "sourceLocation": "SummaryView.html" 
                    } 
           }       
         `````
 
 
*   **Step 9:** Create the Kaizala Action package 
    * Zip all the files into a single zip file 
    * Make sure that the zip does not include another directory inside it – but the files are present at the root directory of the zip

*   **Step 10:** Log in to the Kaizala Management Portal  
    * Open a browser window and navigate to https://manage.kaiza.la/
    * On the top left corner, click on “Sign In” 
    * Enter your Office365 credentials to log in to the portal. If requested, grant permissions to the management portal to access your profile information (needed only for the first time) 
    * Tap on “Add Phone number” on the top right hand corner & verify your phone number 

*   **Step 11:** Upload the action package  
    * Navigate to “Actions” using the left Navbar 
    * From the drop-down on the right – choose “Import Action” and click Start 
    * Click on upload – and select the zip file you created 
    * Click on import
    * Once the package is successfully imported, confirm by browsing to Actions again.You should see your Action listed under “created by this Id”
    * You can test this Action by following steps [here](test.md)

*   **Step 12:** Create a new Kaizala Group  
    * On Kaizala Management portal, navigate to “Groups” using the left navbar 
    * Tap on “Create Group” 
    * Name the group “Kaizala Actions Testing” 
    * Verify that the group appears on your Kaizala app

*   **Step 13:** Publish the Action to the Group  
    * Navigate to “Groups” using the left Navbar 
    * Tap on the group name you created in Step 13 
    * Tap on the “Actions” tab 
    * Select the Action you created in Step 12 & click “Add Action”. You should now see your custom Kaizala Action appearing on the Discover tab

*   **Step 14:** Use custom Kaizala Action  
    * Add the custom Action to your palette and use it in your group. 

 
 
 
 
 
