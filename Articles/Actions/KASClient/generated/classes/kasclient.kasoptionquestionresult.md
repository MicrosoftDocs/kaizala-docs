[type-doc](../README.md) > [KASClient](../modules/kasclient.md) > [KASOptionQuestionResult](../classes/kasclient.kasoptionquestionresult.md)

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

*Defined in model/KASOptionQuestionResult.ts:7*

#### Type declaration

___
<a id="questionid"></a>

###  questionId

**● questionId**: *`number`* = 0

*Inherited from [KASQuestionResult](kasclient.kasquestionresult.md).[questionId](kasclient.kasquestionresult.md#questionid)*

*Defined in model/KASQuestionResult.ts:10*

___
<a id="questiontitle"></a>

###  questionTitle

**● questionTitle**: *`string`* = ""

*Inherited from [KASQuestionResult](kasclient.kasquestionresult.md).[questionTitle](kasclient.kasquestionresult.md#questiontitle)*

*Defined in model/KASQuestionResult.ts:4*

___
<a id="questiontype"></a>

###  questionType

**● questionType**: *[KASQuestionType](../enums/kasclient.kasquestiontype.md)* =  KASQuestionType.None

*Inherited from [KASQuestionResult](kasclient.kasquestionresult.md).[questionType](kasclient.kasquestionresult.md#questiontype)*

*Defined in model/KASQuestionResult.ts:7*

___

## Methods

<a id="getresultsorder"></a>

###  getResultsOrder

▸ **getResultsOrder**(): `number`[]

*Defined in model/KASOptionQuestionResult.ts:13*

Gets all the option ids sorted in their total responses count (descending)

**Returns:** `number`[]
list of all the option ids

___
<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*): [KASOptionQuestionResult](kasclient.kasoptionquestionresult.md)

*Overrides [KASQuestionResult](kasclient.kasquestionresult.md).[fromJSON](kasclient.kasquestionresult.md#fromjson)*

*Defined in model/KASOptionQuestionResult.ts:27*

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASOptionQuestionResult](kasclient.kasoptionquestionresult.md)

___

