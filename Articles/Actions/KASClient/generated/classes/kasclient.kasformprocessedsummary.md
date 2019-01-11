[](../README.md) > [KASClient](../modules/kasclient.md) > [KASFormProcessedSummary](../classes/kasclient.kasformprocessedsummary.md)

# Class: KASFormProcessedSummary

## Hierarchy

**KASFormProcessedSummary**

## Index

### Properties

* [json](kasclient.kasformprocessedsummary.md#json)
* [nonRespondersInConversation](kasclient.kasformprocessedsummary.md#nonrespondersinconversation)
* [results](kasclient.kasformprocessedsummary.md#results)
* [targetResponderCount](kasclient.kasformprocessedsummary.md#targetrespondercount)
* [totalResponseCount](kasclient.kasformprocessedsummary.md#totalresponsecount)


### Methods

* [fromJSON](kasclient.kasformprocessedsummary.md#fromjson)




---

## Properties

<a id="json"></a>

###  json

**● json**: *`JSON`*

___




<a id="nonrespondersinconversation"></a>

###  nonRespondersInConversation

**● nonRespondersInConversation**: *`string`[]* =  []


How many in the conversation did not respond


___




<a id="results"></a>

###  results

**● results**: *`object`*


Aggregated result for aggregative questions Dictionary<QuestionId: number, Result: KASQuestionResult>

#### Type declaration

___




<a id="targetrespondercount"></a>

###  targetResponderCount

**● targetResponderCount**: *`number`* = 0


How many in the conversation were assigned to respond to this form


___




<a id="totalresponsecount"></a>

###  totalResponseCount

**● totalResponseCount**: *`number`* = 0


How many total responses were received for the form, considering multiple responses from one person


___





## Methods

<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`JSON`*): [KASFormProcessedSummary](kasclient.kasformprocessedsummary.md)

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `JSON` |

**Returns:** [KASFormProcessedSummary](kasclient.kasformprocessedsummary.md)

___





