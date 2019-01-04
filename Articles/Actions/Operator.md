# Chat Card customization - Operators 

In some scenarios, there may arise a need where different users may need to view different chat card, that may be based on some attributes. In order to enable such scenarios, Kaizala provides Operators, that enables Action Creators to personalize chat card views for the same Action instance differently for different scenarios/users.

## Let's take an example:

Let's say we want to show the card view differently to sender than its receivers. Using Operators we can achieve this scenario easily, below is the custom chat view JSON for this:  


```json

                  { 

                      "schemaVersion": 3, 

                      "schema": { 

                        "type": "container", 

                        "layout": "vertical", 

                        "children": [ 

                          { 

                            "type": "text", 

                            "string": "Title: ${Form.title}" 

                          }, 

                          { 

                            "type": "text", 

                            "string": "Who am I: ${Operators.custom_text}" 

                          } 

                        ] 

                      }, 

                      "Operators": { 

                        "custom_text": { 

                          "operator": "conditional_value", 

                          "condition": { 

                            "operator": "is_it_me", 

                            "value": { 

                              "operator": "property_value", 

                              "property": "creator", 

                              "src": "local" 

                            } 

                          }, 

                          "value": "Sender", 

                          "default": "Receiver" 

                        } 

                      } 

                  } 
```

Here you can observe that operator "conditional_value"  get Boolean value from  nested operator "is_it_me" which further nested with operator "property_value". Similarly, this can easily be extended to any of such scenarios, even a complex one. 
Additionally, the following entry must be added to the package manifest: ActionStoreSchema: "<name of the action store schema definition file>". For more details, refer to [package Manifest JSON Schema](package_manifest_schema.json) .


 
## List of supported operators: 

> **Note** : the variables x, y, z used in the syntax examples, can either be simple values or result returned by nested operators 


| Operator Name	|Parameter Name	|Parameter Type	|Functionality	|Syntax	|Minimized Syntax |	Note |
|--------|------|------|----|----|----|----|
|Conditional Value	|1. Condition 2. Value 3. Default|1. Boolean 2. Json value 3. Json value | This operator is used to return a specified value, if a defined condition is true. If the condition is false, it returns the false.|{</br>"operator": "conditional_value","condition": x,"value": {   y   },"default": {   z   }</br>}| [ "conditional_value", X, Y, Z] ||
|Equals	|1. Value  2.Value |	1. String	2.String |This operator returns true if the provided values (value1, value2) are equal. Otherwise it returns false |	{</br>"operator": "eq","value1": x,"value2": y </br>} |["eq", x, y] ||
|FormatProfileName	|1. Property 2. Src |1. String	2.PropertyType| Gets the Property from the Src 'PropertyType' and formats the list of userIds as:</br></br>'<Name of User 1> & n more' </br></br>n is the number of users present in the list - 1 |{</br>"operator":"format_profile_names",</br>"property": x, "src":PropertyType</br>}|["format_profile_names", PropertyType, x] |PropertyType</br>{</br>  local,server</br>} </br></br>1. This operator assumes the property x provided returns array of userIds </br></br>2. UserName1 is you if the current logged-in user is present in the list of userIds.|
|FormatString|1. Format 2. Agrs|1. String 2.Array of arguments expected by the Format string|This operator allows to format a string using format specifiers.</br></br>This operator is same as any other format string operator present in cpp or java |{</br>"operator": "format_string","format": x,"args": [y, z ...]</br>}|["format_string", x, [y, z ...]]|X can contain specifiers like %s, %d etc and the operators expects the arguments to be present of same type in same order </br></br>For e.g. String can be</br>{</br>"operator": "format_string",</br>"format": "My name is %s and my age is %d",</br>"args": [y, z]</br>}</br></br>Where y is a string variable and z is a integer|
|IsCurrentUser|1.Value|1. uuid Compares the provided uuid (UserId) with the uuid (UserId) of current logged-in user. It returns true if it matches and returns false otherwise |{</br>"operator": "is_it_me",</br>"value": x</br>}|["is_it_me"x]|
|JSONPathValue|1. 1. Entity 2.Path|1.EntityType 2.Valid json path| Fetches the value residing at the key in entity json of the given type.  It returns first value that is encountered in the path. |{</br>"operator": "jsonpath_value",</br>"entity": EntityType,</br>"path": ValidJsonPath</br>}|["jsonpath_value", EntityType, ValidJsonPath]|{</br>"operator":</br>"jsonpath_value",</br>"entity": Message,</br>"path": "$..SenderName"</br>}</br></br>"$.." Traverse recursively</br></br>"$." Traverse only 1st level of entity|
|MessageConversationName|1. Value|1. messageId|Returns the conversation name to which the message with given messageId belongs to.|{"operator": "message_conversation_name","value": x}|["message_conversation_name",x]|
|MessageCreationTime|1. Value|1. messageId|Returns the human readable timestamp string for the creation timestamp of the message with given messageId |{</br>"operator": "message_creation_time",</br>"value": x</br>}|["message_creation_time", x]|
|ProfileName|1. id|1. uuid|Return the Display name of the user when uuid (UserId) is provided |{</br>"operator": "profile_name","id": x</br>}|["profile_name", x]|
|PropertyValue|1.Src 2.Property|1.PropertyType 2.String|Gets the Property from the Src PropertyType|{</br>"operator": "property_value",</br>"property": x,"src": PropertyType</br>}|["property_value", PropertyType, x]|PropertyType</br></br>{</br>local,server</br>}|
|AdditionOperation |1. Arg1 | 1. Array of arguments needed by addition operation |It evaluates all the values inside the args, and adds them |{</br>"operator":"addition",</br>"args":[{</br>"operator"..</br>},2,4]</br>} |["addition", [1, 2, 3]]|Make sure to evaluate args which result in floating type|
|SubtractionOperation |1.Arg1 2.Arg2|1. Argument from which to subtract</br>2. Argument which needs to be subtracted|It evaluates both the values inside the args, and subtracts the second one from the first one|{</br>"operator":"subtraction",</br>"arg1":</br>{</br>"operator"..</br>}, </br>"arg2":2</br>}|["subtraction", [4, 3]] |Make sure to evaluate args which result in floating type|
MultiplicationOperation |1. Arg1|1. Array of arguments needed by multiplication operation | It evaluates all the values inside the args, and multiplies them |{</br>"operator":"multiplication", </br>"args":[</br>{</br>"operator"..</br>},2,4]</br>}|["multiplication", [1, 2, 3]|Make sure to evaluate args which result in floating type|
|DivisionOperation |1. Arg1</br>2. Arg2|1. Argument from which to divide </br>2. Argument which needs to be divided  |It evaluates both the values inside the args, and divides the second one from the first one|{</br>"operator":"division",</br>"arg1":</br>{</br>"operator"..</br>}, </br>"arg2":2</br>} |["division", [4, 3]] |Make sure to evaluate args which result in floating type |
|ModuloOperation |1. Arg1 </br>2. Arg2|1. Argument from which to divide </br> 2. Argument which needs to be divided to get the remainder|It evaluates both the values inside the args, and divides the second one from the first one and returns the remainder |{</br>"operator":"modulo",</br>"arg1":</br>{</br>"operator"..</br>},</br>"arg2":2</br>}|["modulo", [4, 3]] |Make sure to evaluate args which result in floating type |

