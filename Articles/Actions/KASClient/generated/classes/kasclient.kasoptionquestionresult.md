[](../README.md) > [KASClient](../modules/kasclient.md) > [KASOptionQuestionResult](../classes/kasclient.kasoptionquestionresult.md)

# Class: KASOptionQuestionResult

## Hierarchy

 [KASQuestionResult](kasclient.kasquestionresult.md)

**↳ KASOptionQuestionResult**

## Index

### Properties

* [optionResults](kasclient.kasoptionquestionresult.md#optionresults)
* [questionId](kasclient.kasoptionquestionresult.md#questionid)
* [questionTitle](kasclient.kasoptionquestionresult.md#questiontitle)
* [questionType](kasclient.kasoptionquestionresult.md#questiontype)


### Methods

* [getResultsOrder](kasclient.kasoptionquestionresult.md#getresultsorder)
* [fromJSON](kasclient.kasoptionquestionresult.md#fromjson)




---

## Properties

<a id="optionresults"></a>

###  optionResults

**● optionResults**: *`object`*


For SingleSelect/MultiSelect question, the result will be option id versus their counts Dictionary<OptionId: number, OptionResult: KASOptionResult>

#### Type declaration

___




<a id="questionid"></a>

###  questionId

**● questionId**: *`number`* = 0


Index of the question


___




<a id="questiontitle"></a>

###  questionTitle

**● questionTitle**: *`string`* = ""


Title of the question


___




<a id="questiontype"></a>

###  questionType

**● questionType**: *[KASQuestionType](../enums/kasclient.kasquestiontype.md)* =  KASQuestionType.None


Type of the question


___





## Methods

<a id="getresultsorder"></a>

###  getResultsOrder

▸ **getResultsOrder**(): `number`[]


Gets all the option ids sorted in their total responses count (descending)


**Returns:** `number`[]
list of all the option ids

___




<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*): [KASOptionQuestionResult](kasclient.kasoptionquestionresult.md)

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASOptionQuestionResult](kasclient.kasoptionquestionresult.md)

___





