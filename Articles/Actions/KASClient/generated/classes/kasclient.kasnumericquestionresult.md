[](../README.md) > [KASClient](../modules/kasclient.md) > [KASNumericQuestionResult](../classes/kasclient.kasnumericquestionresult.md)

# Class: KASNumericQuestionResult

## Hierarchy

 [KASQuestionResult](kasclient.kasquestionresult.md)

**↳ KASNumericQuestionResult**

## Index

### Properties

* [average](kasclient.kasnumericquestionresult.md#average)
* [questionId](kasclient.kasnumericquestionresult.md#questionid)
* [questionTitle](kasclient.kasnumericquestionresult.md#questiontitle)
* [questionType](kasclient.kasnumericquestionresult.md#questiontype)
* [sum](kasclient.kasnumericquestionresult.md#sum)


### Methods

* [fromJSON](kasclient.kasnumericquestionresult.md#fromjson)




---

## Properties

<a id="average"></a>

###  average

**● average**: *`number`* = 0

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




<a id="sum"></a>

###  sum

**● sum**: *`number`* = 0


For Numeric questions the aggregated result will be sum, and average of all the responses


___





## Methods

<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*): [KASNumericQuestionResult](kasclient.kasnumericquestionresult.md)

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASNumericQuestionResult](kasclient.kasnumericquestionresult.md)

___





