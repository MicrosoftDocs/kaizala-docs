[type-doc](../README.md) > [KASClient](../modules/kasclient.md) > [KASFormFlatSummary](../classes/kasclient.kasformflatsummary.md)

# Class: KASFormFlatSummary

## Hierarchy

**KASFormFlatSummary**

## Index

### Properties

* [conversationId](kasclient.kasformflatsummary.md#conversationid)
* [formId](kasclient.kasformflatsummary.md#formid)
* [json](kasclient.kasformflatsummary.md#json)

### Methods

* [getAllResponses](kasclient.kasformflatsummary.md#getallresponses)
* [getQuestionResponsesForUserId](kasclient.kasformflatsummary.md#getquestionresponsesforuserid)
* [getRespondedUserIds](kasclient.kasformflatsummary.md#getrespondeduserids)
* [getResponsesForUserId](kasclient.kasformflatsummary.md#getresponsesforuserid)
* [getTotalResponseCount](kasclient.kasformflatsummary.md#gettotalresponsecount)
* [fromJSON](kasclient.kasformflatsummary.md#fromjson)

---

## Properties

<a id="conversationid"></a>

###  conversationId

**● conversationId**: *`string`* = ""

*Defined in model/KASFormFlatSummary.ts:7*

___
<a id="formid"></a>

###  formId

**● formId**: *`string`* = ""

*Defined in model/KASFormFlatSummary.ts:4*

___
<a id="json"></a>

###  json

**● json**: *`JSON`*

*Defined in model/KASFormFlatSummary.ts:9*

___

## Methods

<a id="getallresponses"></a>

###  getAllResponses

▸ **getAllResponses**(): `__type`

*Defined in model/KASFormFlatSummary.ts:60*

Gets all the responses of all the users

**Returns:** `__type`

___
<a id="getquestionresponsesforuserid"></a>

###  getQuestionResponsesForUserId

▸ **getQuestionResponsesForUserId**(userId: *`string`*, questionId: *`number`*): `string`[]

*Defined in model/KASFormFlatSummary.ts:30*

Gets all the responses of a user against a specific question

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| userId | `string` |  the unique id of the user |
| questionId | `number` |  the id of the question |

**Returns:** `string`[]
list of all answers given by the user for that question

___
<a id="getrespondeduserids"></a>

###  getRespondedUserIds

▸ **getRespondedUserIds**(): `string`[]

*Defined in model/KASFormFlatSummary.ts:20*

Gets all the user ids who responded to the form

**Returns:** `string`[]
list of all the responded user ids

___
<a id="getresponsesforuserid"></a>

###  getResponsesForUserId

▸ **getResponsesForUserId**(userId: *`string`*): `__type`

*Defined in model/KASFormFlatSummary.ts:47*

Gets all the responses of a user to a form

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| userId | `string` |  the unique id of the user |

**Returns:** `__type`
question id to list of answers

___
<a id="gettotalresponsecount"></a>

###  getTotalResponseCount

▸ **getTotalResponseCount**(): `number`

*Defined in model/KASFormFlatSummary.ts:93*

Gets number of all responses by all users

**Returns:** `number`
number of all responses

___
<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*, isResponseAppended: *`boolean`*): [KASFormFlatSummary](kasclient.kasformflatsummary.md)

*Defined in model/KASFormFlatSummary.ts:102*

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |
| isResponseAppended | `boolean` |

**Returns:** [KASFormFlatSummary](kasclient.kasformflatsummary.md)

___

