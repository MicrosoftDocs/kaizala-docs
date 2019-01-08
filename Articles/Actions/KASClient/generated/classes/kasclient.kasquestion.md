[](../README.md) > [KASClient](../modules/kasclient.md) > [KASQuestion](../classes/kasclient.kasquestion.md)

# Class: KASQuestion

## Hierarchy

**KASQuestion**

## Index

---

### Properties

* [config](kasclient.kasquestion.md#config)
* [displayType](kasclient.kasquestion.md#displaytype)
* [id](kasclient.kasquestion.md#id)
* [isEditable](kasclient.kasquestion.md#iseditable)
* [isExcludedFromReporting](kasclient.kasquestion.md#isexcludedfromreporting)
* [isInvisible](kasclient.kasquestion.md#isinvisible)
* [isResponseOptional](kasclient.kasquestion.md#isresponseoptional)
* [options](kasclient.kasquestion.md#options)
* [title](kasclient.kasquestion.md#title)
* [type](kasclient.kasquestion.md#type)
* [valif](kasclient.kasquestion.md#valif)
* [visif](kasclient.kasquestion.md#visif)

### Methods

* [getAPICompatibleQuestionType](kasclient.kasquestion.md#getapicompatiblequestiontype)
* [toAPICompatibleJSON](kasclient.kasquestion.md#toapicompatiblejson)
* [toClientJSON](kasclient.kasquestion.md#toclientjson)
* [toJSON](kasclient.kasquestion.md#tojson)
* [validateResponse](kasclient.kasquestion.md#validateresponse)
* [fromJSON](kasclient.kasquestion.md#fromjson)

---

## Properties

<a id="config"></a>

###  config

**● config**: *[KASQuestionConfig](kasclient.kasquestionconfig.md)* =  null

___
<a id="displaytype"></a>

###  displayType

**● displayType**: *[KASQuestionDisplayType](../enums/kasclient.kasquestiondisplaytype.md)* =  KASQuestionDisplayType.None

___
<a id="id"></a>

###  id

**● id**: *`number`* = 0

___
<a id="iseditable"></a>

###  isEditable

**● isEditable**: *`boolean`* = true

___
<a id="isexcludedfromreporting"></a>

###  isExcludedFromReporting

**● isExcludedFromReporting**: *`boolean`* = false

___
<a id="isinvisible"></a>

###  isInvisible

**● isInvisible**: *`boolean`* = false

___
<a id="isresponseoptional"></a>

###  isResponseOptional

**● isResponseOptional**: *`boolean`* = false

___
<a id="options"></a>

###  options

**● options**: *[KASQuestionOption](kasclient.kasquestionoption.md)[]* =  []

___
<a id="title"></a>

###  title

**● title**: *`string`* = ""

___
<a id="type"></a>

###  type

**● type**: *[KASQuestionType](../enums/kasclient.kasquestiontype.md)* =  KASQuestionType.None

___
<a id="valif"></a>

###  valif

**● valif**: *[KASValidationRule](kasclient.kasvalidationrule.md)* =  null

___
<a id="visif"></a>

###  visif

**● visif**: *[KASVisibilityRule](kasclient.kasvisibilityrule.md)* =  null

___

## Methods

<a id="getapicompatiblequestiontype"></a>

###  getAPICompatibleQuestionType

▸ **getAPICompatibleQuestionType**(type: *`string`*): `string`

**Parameters:**

| Name | Type |
| ------ | ------ |
| type | `string` |

**Returns:** `string`

___
<a id="toapicompatiblejson"></a>

###  toAPICompatibleJSON

▸ **toAPICompatibleJSON**(): `JSON`

**Returns:** `JSON`

___
<a id="toclientjson"></a>

###  toClientJSON

▸ **toClientJSON**(): `JSON`

**Returns:** `JSON`

___
<a id="tojson"></a>

###  toJSON

▸ **toJSON**(): `JSON`

**Returns:** `JSON`

___
<a id="validateresponse"></a>

###  validateResponse

▸ **validateResponse**(response: *`string`*): [KASQuestionValidationResponse](kasclient.kasquestionvalidationresponse.md)

**Parameters:**

| Name | Type |
| ------ | ------ |
| response | `string` |

**Returns:** [KASQuestionValidationResponse](kasclient.kasquestionvalidationresponse.md)

___
<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*): [KASQuestion](kasclient.kasquestion.md)

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASQuestion](kasclient.kasquestion.md)

___

