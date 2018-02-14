# Customizing ChatCanvasCardView

Unlike the creation, response and summary views that are html, chat views are native views. To customize the chat card view, you will need to provide a json of the card layout as well as the values in the view. In the absence of a customized chat canvas card view, the default would be chat card view with the text of app title. 

## Views and their supported properties
Below are different types of sub-views/widgets along with their customizable properties. Few properties are marked with <sup>iOS</sup>  indicating that they are applicable only on iOS _(and will have no effect on android)_.

### Container / View

<ol>
<li>id (optional, but must be unique)</li>
<li>visible<sup>iOS</sup></li>
<li>type _(any of the sub-view types we are mentioning here)_</li>
<li>margin / marginTop / marginRight / marginBottom / marginLeft</li>
<li>padding / paddingTop / paddingRight / paddingBottom / paddingLeft</li>
<li>width</li>
<li>height</li>
<li>weight _(%ratio of parent view's width/height in case of horizontal/vertical layouts respectively)_</li>
<li>backgroundColor  _(only hex code allowed here)_</li>
<li>cornerRadius</li>
<li>borderWidthiOS / borderColoriOS</li>
<li>children _(array of sub-views)_</li>
<li>layout _(vertical / horizontal � when unspecified, defaults to vertical)_</li>
<li>verticalAlignment _(top / bottom / center / stretchiOS - how children will be aligned vertically)_</li>
<li>horizontalAlignment _(left / right / center / spaceBetween<sup>iOS</sup> / spaceAround<sup>iOS</sup>) - how children will be aligned horizontally._</li>
<li>initialHeight<sup>iOS</sup> � _an iOS only property used in the topmost container that is used to render the card before the accurate dimension is ascertained. It is strongly advised to use this property for a smoother experience!_</li>
</ol>

### Text

<ol>
<li>id (optional, but must be unique)</li>
<li>visible<sup>iOS</sup></li>
<li>type _(any of the sub-view types we are mentioning here)_</li>
<li>margin / marginTop / marginRight / marginBottom / marginLeft</li>
<li>padding / paddingTop / paddingRight / paddingBottom / paddingLeft</li>
<li>width</li>
<li>height</li>
<li>weight _(%ratio of parent view's width/height in case of horizontal/vertical layouts respectively)_</li>
<li>backgroundColor  _(only hex code allowed here)_</li>
<li>cornerRadius</li>
<li>borderWidthiOS / borderColoriOS</li>
<li>string</li>
<li>fontSize _(font family is always System's default, to avoid rendering issues)_</li>
<li>textColor _(only hex code allowed here)_</li>
<li>ellipsizeMode _(head / middle / tail)_</li>
<li>maxNumberOfLines _(0 for no limit, else text will be truncated as per ellipsizeMode)_</li>
</ol>


### Image

<ol>
<li>id (optional, but must be unique)</li>
<li>visible<sup>iOS</sup></li>
<li>type _(any of the sub-view types we are mentioning here)_</li>
<li>margin / marginTop / marginRight / marginBottom / marginLeft</li>
<li>padding / paddingTop / paddingRight / paddingBottom / paddingLeft</li>
<li>width</li>
<li>height</li>
<li>weight _(%ratio of parent view's width/height in case of horizontal/vertical layouts respectively)_</li>
<li>backgroundColor  _(only hex code allowed here)_</li>
<li>cornerRadius</li>
<li>borderWidthiOS / borderColoriOS</li>
<li>source</li>
<li>contentMode _(aspectFit / aspectFill / stretch / repeat<sup>iOS</sup>)_</li>
</ol>



## Binding data with views
* __Form__
  * $\{Form.title}
  * $\{Form.expiry} - _output is a date-time string_
  * $\{Form.questions}
  * $\{Form.questions.length}
  * $\{Form.questions[questionId].title}
  * $\{Form.questions[questionId].options}
  * $\{Form.questions[questionId].options.length}
  * $\{Form.questions[questionId].options[optionId].text}
  * $\{Form.questions[questionId].options[optionId].pictureUrl}
  * $\{Form.properties}
  * $\{Form.properties.length}
  * $\{Form.properties[propertyName]}
  * $\{Form.properties[propertyName].value}
  * $\{Form.properties[propertyName].length} - _for Array/Set type property_
* __MyLatestResponse__
  * $\{MyLatestResponse.sendTime} - _output is a date-time string_
  * $\{MyLatestResponse.questionToAnswerMap[questionId]}
* __Summary__
  * $\{Summary.totalResponseCount}
  * $\{Summary.totalParticipantsCount}
  * $\{Summary.targetResponderCount}

Also one can use these variables as placeholders, like:  
_"Thanks for your news report: ${Form.properties[newsDescription].value}"_

## Operations

In some scenarios, there may arise a need where different users may need to view different chat card, that may be based on some attributes. In order to enable such scenarios, Kaizala provides [operators](Operator.md), that enables Action Creators to personalise chat card views for the same Action instance differently for different scenarios/users.

For example, you may choose to show a different card view for users who have not completed the job, and a different card view for users who have completed the job. This can be extended to any type of scenarios that may arise.

## How to provide the json schema
In the manifest _(package.json)_ file of a package put the JSON file name under **sourceLocation** key in **ChatCanvasCardView**
Below is a sample snapshot from package.json:

![snapshot of package.json](./chatcardviewjson.png)

## Example ChatCanvasCardView source file
```json
{
    "schemaVersion": 1,
    "schema": {
        "type": "container",
        "initialHeight": 300,
        "layout": "vertical",
        "children": [
            {
                "type": "text",
                "paddingLeft": 10,
                "paddingRight": 10,
                "string": "${Form.properties[Property1].value}",
                "fontSize": 18,
                "fontStyle": "bold",
                "textColor": "#CE222E",
                "textAlignment": "left",
                "maxNumberOfLines": 2,
                "marginBottom": 10
            },
            {
                "type": "image",
                "height": 160,
                "source": "${Form.properties[CoverImageProperty].value}",
                "contentMode": "aspectFit",
                "backgroundColor": "#263749",
                "marginBottom": 10
            },
            {
                "type": "text",
                "paddingLeft": 10,
                "paddingRight": 10,
                "string": "${Form.properties[Property2].value}",
                "fontSize": 18,
                "fontStyle": "bold",
                "textColor": "#32495f",
                "textAlignment": "left",
                "maxNumberOfLines": 4,
                "marginBottom": 0
            }
        ]
    }
}
