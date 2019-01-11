[](../README.md) > [KASClient](../modules/kasclient.md) > [KASOptionResult](../classes/kasclient.kasoptionresult.md)

# Class: KASOptionResult

## Hierarchy

**KASOptionResult**

## Index

### Properties

* [optionId](kasclient.kasoptionresult.md#optionid)
* [optionTitle](kasclient.kasoptionresult.md#optiontitle)
* [responderToResponseCount](kasclient.kasoptionresult.md#respondertoresponsecount)
* [totalResponsesCount](kasclient.kasoptionresult.md#totalresponsescount)


### Methods

* [fromJSON](kasclient.kasoptionresult.md#fromjson)




---

## Properties

<a id="optionid"></a>

###  optionId

**● optionId**: *`number`* = 0


Index of the option


___




<a id="optiontitle"></a>

###  optionTitle

**● optionTitle**: *`string`* = ""


Title of the option


___




<a id="respondertoresponsecount"></a>

###  responderToResponseCount

**● responderToResponseCount**: *`object`*


A map of user ids against their response count Dictionary<UserId: string, ResponseCount: number>

#### Type declaration

___




<a id="totalresponsescount"></a>

###  totalResponsesCount

**● totalResponsesCount**: *`number`* = 0


How many have chosen this option


___





## Methods

<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*): [KASOptionResult](kasclient.kasoptionresult.md)

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASOptionResult](kasclient.kasoptionresult.md)

___





