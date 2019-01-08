[type-doc](../README.md) > [KASClient](../modules/kasclient.md) > [KASQuestion](../classes/kasclient.kasquestion.md)

# Class: KASQuestion

## Hierarchy

**KASQuestion**

## Index

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

*Defined in model/KASQuestion.ts:13*

___
<a id="displaytype"></a>

###  displayType

**● displayType**: *[KASQuestionDisplayType](../enums/kasclient.kasquestiondisplaytype.md)* =  KASQuestionDisplayType.None

*Defined in model/KASQuestion.ts:16*

___
<a id="id"></a>

###  id

**● id**: *`number`* = 0

*Defined in model/KASQuestion.ts:4*

___
<a id="iseditable"></a>

###  isEditable

**● isEditable**: *`boolean`* = true

*Defined in model/KASQuestion.ts:22*

___
<a id="isexcludedfromreporting"></a>

###  isExcludedFromReporting

**● isExcludedFromReporting**: *`boolean`* = false

*Defined in model/KASQuestion.ts:25*

___
<a id="isinvisible"></a>

###  isInvisible

**● isInvisible**: *`boolean`* = false

*Defined in model/KASQuestion.ts:19*

___
<a id="isresponseoptional"></a>

###  isResponseOptional

**● isResponseOptional**: *`boolean`* = false

*Defined in model/KASQuestion.ts:28*

___
<a id="options"></a>

###  options

**● options**: *[KASQuestionOption](kasclient.kasquestionoption.md)[]* =  []

*Defined in model/KASQuestion.ts:31*

___
<a id="title"></a>

###  title

**● title**: *`string`* = ""

*Defined in model/KASQuestion.ts:7*

___
<a id="type"></a>

###  type

**● type**: *[KASQuestionType](../enums/kasclient.kasquestiontype.md)* =  KASQuestionType.None

*Defined in model/KASQuestion.ts:10*

___
<a id="valif"></a>

###  valif

**● valif**: *[KASValidationRule](kasclient.kasvalidationrule.md)* =  null

*Defined in model/KASQuestion.ts:34*

___
<a id="visif"></a>

###  visif

**● visif**: *[KASVisibilityRule](kasclient.kasvisibilityrule.md)* =  null

*Defined in model/KASQuestion.ts:37*

___

## Methods

<a id="getapicompatiblequestiontype"></a>

###  getAPICompatibleQuestionType

▸ **getAPICompatibleQuestionType**(type: *`string`*): `string`

*Defined in model/KASQuestion.ts:39*

**Parameters:**

| Name | Type |
| ------ | ------ |
| type | `string` |

**Returns:** `string`

___
<a id="toapicompatiblejson"></a>

###  toAPICompatibleJSON

▸ **toAPICompatibleJSON**(): `JSON`

*Defined in model/KASQuestion.ts:100*

**Returns:** `JSON`

___
<a id="toclientjson"></a>

###  toClientJSON

▸ **toClientJSON**(): `JSON`

*Defined in model/KASQuestion.ts:66*

**Returns:** `JSON`

___
<a id="tojson"></a>

###  toJSON

▸ **toJSON**(): `JSON`

*Defined in model/KASQuestion.ts:57*

**Returns:** `JSON`

___
<a id="validateresponse"></a>

###  validateResponse

▸ **validateResponse**(response: *`string`*): [KASQuestionValidationResponse](kasclient.kasquestionvalidationresponse.md)

*Defined in model/KASQuestion.ts:202*

**Parameters:**

| Name | Type |
| ------ | ------ |
| response | `string` |

**Returns:** [KASQuestionValidationResponse](kasclient.kasquestionvalidationresponse.md)

___
<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*): [KASQuestion](kasclient.kasquestion.md)

*Defined in model/KASQuestion.ts:117*

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASQuestion](kasclient.kasquestion.md)

___

