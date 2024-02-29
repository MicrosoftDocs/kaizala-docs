---
description: Learn to create an action using component card controls with Microsoft's detailed tutorial. Master text boxes, dropdowns, date controls, and more.
---
# Create an Action using Component Card Controls 

## Overview
In this article, we will cover the various component cards controls which can be used in an action using component card framework.

The following are the controls supported
* Text Box / Numeric Text Box
* Location
* Attachment Box
* Single Select Check-Box
* Slider with Text Box
* Date Control
* Time Control
* Text Area
* Dropdown


We will list down the file changes needed to enable the control in a custom card. You will need to add the following details in the corresponding files as given below.

## Creation view
The following contains the code snippet that should go inside a page (eg: \<div id='page_1'\>...\</div\>) in "CreationView.html".

* **Text Box / Numeric Text Box:**
Each control has a LABEL ID (to prompt the user as to what data the control is for) and an INPUT ID (to point to the value that needs to be inserted). 
For the numeric text box, the code snippet remains the same. Only change required is that the input type should be "number" instead of "text".

  `````
    <div class='section-div'>
    <div id='LABEL1' class='field-label'>
    </div>
    <input id='INPUT1' type='text' contenteditable='true' class='textbox-1'>
    </div>
  `````

* **Location:** 
This control has a LABEL ID (to prompt the user as to what data the control is for).

  `````
    <div class='section-div'>
    <div id='LABEL21' class='field-label'>
    </div>
    <img class='location-image' id='location'>
    <div style='padding: 8px 15pt 15pt; display: inline-flex;'>
    <div class='location-div1'>
    <label class='location-address' id='location_text'>
    </label>
    </div>
    <div class='location-div2'>
    <label id='refresh-location-text' onclick='refreshLocation();' class='refresh-location-text'>
    </label>
    </div>
    </div>
    </div>
  `````
  
* **Attachment Box:**
This control has a LABEL ID (to prompt the user as to what data the control is for) and an INPUT ID (to point to the value that needs to be inserted).
	
  `````	
	  <div class='section-div'>
	  <div id='LABEL4' class='field-label'>
	  </div>
	  <div id='INPUT4' class='scroll-div' title='Attachments'>
	  <div class='horizontal-div'>
	  <div class='attachment-div'>
	  <img class='section-img' onclick='addAttachment()'>
	  </div>
	  </div>
	  </div>
	  </div>
  `````
 
* **Single select Check-Box:**
This control has a LABEL ID (to prompt the user as to what data the control is for) and a CHECKBOX ID (to point to the value that needs to be inserted). 
The ID should be prefixed with CHECKBOX (eg: CHECKBOX1). The IDs of the individual options should be mapped to the parent checkbox. 
Also, this control cannot be made optional as by default, the first option will be selected when the form is rendered.

  `````
	  <div class='section-div'>
	  <div id='LABEL5' class='field-label'>
	  </div>
	  <div class='option-div' id='CHECKBOX1'>
	  <div class='single-select-rounded'>
	  <label id='CHECKBOX1_1' class='selected-label'>
	  </label>
	  </div>
	  <div class='single-select-rounded'>
	  <label id='CHECKBOX1_2' class='unselected-label'>
	  </label>
	  </div>
	  <div class='single-select-rounded'>
	  <label id='CHECKBOX1_3' class='unselected-label'>
	  </label>
	  </div>
	  </div>
	  </div>
  `````
  
* **Slider with TextBox:**
This control has a LABEL ID (to prompt the user as to what data the control is for) and a INPUT ID (to enter a numerical value directly). 
It cannot be made optional as by default as the slider will always be initialized with a default value.

  `````
    <div class='section-div slider-with-textbox'>
    <div id='LABEL6' class='field-label'>
    </div>
    <input id='INPUT6' type='range' class='slider-bar'>
    <input class='slider-textbox' type='number'>
    </input>
    </div>
  `````

* **Date Control:**
 Each control has a LABEL ID (to prompt the user as to what data the control is for) and an INPUT ID (to point to the value that needs to be inserted).
	
	`````
	    <div class='section-div'>
	    <div id='LABEL7' class='field-label'>
	    </div>
	    <div id='INPUT7' onClick='event_click(this)' class='textbox-1 image_right_date' value=''>
	    </div>
	    <div style='width: 0px; height: 0px; overflow: hidden;'>
	    <input type='date' onChange='change_date_format(this)' class='textbox-1'>
	    </div>
	    </div>
  `````


* **Time Control:**
Each control has a LABEL ID (to prompt the user as to what data the control is for) and an INPUT ID (to point to the value that needs to be inserted).
	
  `````
	  <div class='section-div'>
	  <div id='LABEL8' class='field-label'>
	  </div>
	  <div id='INPUT8' onClick='event_click(this)' class='textbox-1 image_right_time' value=''>
	  </div>
	  <div style='width: 0px; height: 0px; overflow: hidden;'>
	  <input type='time' onChange='change_time_format(this)' class='textbox-1'>
	  </div>
	  </div>
  `````
	
* **Text Area:**
Each control has a LABEL ID (to prompt the user as to what data the control is for) and an INPUT ID (to point to the value that needs to be inserted).

  `````
	<div class='section-div'>
	<div id='LABEL9' class='field-label'>
	</div>
	<textarea id='INPUT9' contenteditable='true' class='text-area'>
	</textarea>
	</div>
  `````
 
* **Dropdown:**
Each control has a LABEL ID (to prompt the user as to what data the control is for) and an INPUT ID (to point to the value that needs to be inserted). 
This control cannot be made optional.

  `````
	  <div class='section-div'>
	  <div id='LABEL10' class='field-label'>
	  </div>
	  <table id='INPUT10' class='feedbackSlderTable' title='TapBasedSlider'>
	  </table>
	  <div class='progressbar-outer-div'>
	  <div class='progressbar-inner-div'>
	  </div>
	  </div>
	  </div>
  `````

## Summary View
This is the code snippet that should go inside container in "SummaryView.html". 
The suffix of ANSWER in the id is the question number in AppModel to which the question has been mapped (starting from 1). 
Below is a an example for any control. The number of answers in the AppModel should be equal to the number of sections in the "SummaryView.html".

  `````
	  <div class='section-div-summary'>
	  <div id='ANSWER_1' class='field-label-summary'>
	  </div>
	  <label class='answer-label'>
	  </label>
	  </div>
  `````	
	
## AppModel File
This is the code snippet that should go inside "AppModel.jsonConfig" where the data model is defined - the title will correspond to the what the Summary View will display corresponding to the actual data entered by the user.
Below is a an example for TextBox control. A similar format needs to be followed for other controls as well. 
Please note that for Attachment the type should be "AttachmentList" and for Location the type should be "Location".
  `````	
	  {
	  "title": "Name",
	  "type": "Text"
	  }
  `````

## Configuration File
	
This is the code snippet that should go inside "Config.js" file. In SUBMIT_IDS you need to put the INPUT ID of the control in the same sequence as the questions are present in the AppModel. 
In case you want to make it optional, please add it in the OPTIONAL_IDS dictionary with corresponding page number - in case nothing in a page is optional, assign an empty array to the corresponding page (as seen in the example for page_2). 
Optional question labels will automatically be appended with the string '(optional)' when the form is rendered. Below is a an example for TextBox control. All controls will have a similar format. 
Please note that for Images and Location, we don't need an entry in SUBMIT_IDS.

  `````
    var SUBMIT_IDS = ['INPUT1'];
    var OPTIONAL_IDS = {
    "page_1": ["INPUT1"],
    "page_2": []
    };// in case you have a page 2 where all questions are mandatory
  `````

## Localized Strings File - strings_en.json
This is the code snippet that should go inside the strings file where the strings are defined. 
For a textbox with ID as INPUT1 there is a label associated which prompts the user as to what the question is; then there is an optional placeholder which appears as a ghost-text inside the textbox. 
This is an example of Textbox control. All controls will have similar format.

  `````
    "LABEL1": "Please enter your name",
    "INPUT1_placeholder": "Tap to enter name"
  `````

