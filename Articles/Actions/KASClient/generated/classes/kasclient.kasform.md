[type-doc](../README.md) > [KASClient](../modules/kasclient.md) > [KASForm](../classes/kasclient.kasform.md)

# Class: KASForm

## Hierarchy

**KASForm**

## Index

### Properties

* [allowSendReminder](kasclient.kasform.md#allowsendreminder)
* [conversationId](kasclient.kasform.md#conversationid)
* [creatorId](kasclient.kasform.md#creatorid)
* [expiry](kasclient.kasform.md#expiry)
* [id](kasclient.kasform.md#id)
* [isAnonymous](kasclient.kasform.md#isanonymous)
* [isGroupLevelAggregationRequired](kasclient.kasform.md#isgrouplevelaggregationrequired)
* [isLocationRequested](kasclient.kasform.md#islocationrequested)
* [isResponseAppended](kasclient.kasform.md#isresponseappended)
* [json](kasclient.kasform.md#json)
* [packageId](kasclient.kasform.md#packageid)
* [properties](kasclient.kasform.md#properties)
* [questions](kasclient.kasform.md#questions)
* [reportType](kasclient.kasform.md#reporttype)
* [title](kasclient.kasform.md#title)
* [type](kasclient.kasform.md#type)
* [version](kasclient.kasform.md#version)
* [visibility](kasclient.kasform.md#visibility)

### Methods

* [getAPICompatibleVisibilityType](kasclient.kasform.md#getapicompatiblevisibilitytype)
* [toAPICompatibleJSON](kasclient.kasform.md#toapicompatiblejson)
* [toClientJSON](kasclient.kasform.md#toclientjson)
* [toJSON](kasclient.kasform.md#tojson)
* [addResponseNotificationForAddRow](kasclient.kasform.md#addresponsenotificationforaddrow)
* [fromJSON](kasclient.kasform.md#fromjson)

---

## Properties

<a id="allowsendreminder"></a>

###  allowSendReminder

**● allowSendReminder**: *[KASFormResultVisibility](../enums/kasclient.kasformresultvisibility.md)* =  KASFormResultVisibility.Sender

*Defined in model/KASForm.ts:31*

___
<a id="conversationid"></a>

###  conversationId

**● conversationId**: *`string`* = ""

*Defined in model/KASForm.ts:7*

___
<a id="creatorid"></a>

###  creatorId

**● creatorId**: *`string`* = ""

*Defined in model/KASForm.ts:13*

___
<a id="expiry"></a>

###  expiry

**● expiry**: *`number`* = 0

*Defined in model/KASForm.ts:22*

___
<a id="id"></a>

###  id

**● id**: *`string`* = ""

*Defined in model/KASForm.ts:4*

___
<a id="isanonymous"></a>

###  isAnonymous

**● isAnonymous**: *`boolean`* = false

*Defined in model/KASForm.ts:19*

___
<a id="isgrouplevelaggregationrequired"></a>

###  isGroupLevelAggregationRequired

**● isGroupLevelAggregationRequired**: *`boolean`* = false

*Defined in model/KASForm.ts:37*

___
<a id="islocationrequested"></a>

###  isLocationRequested

**● isLocationRequested**: *`boolean`* = false

*Defined in model/KASForm.ts:40*

___
<a id="isresponseappended"></a>

###  isResponseAppended

**● isResponseAppended**: *`boolean`* = false

*Defined in model/KASForm.ts:34*

___
<a id="json"></a>

###  json

**● json**: *`JSON`*

*Defined in model/KASForm.ts:57*

___
<a id="packageid"></a>

###  packageId

**● packageId**: *`string`* = ""

*Defined in model/KASForm.ts:10*

___
<a id="properties"></a>

###  properties

**● properties**: *[KASFormProperty](kasclient.kasformproperty.md)[]* =  []

*Defined in model/KASForm.ts:52*

___
<a id="questions"></a>

###  questions

**● questions**: *[KASQuestion](kasclient.kasquestion.md)[]* =  []

*Defined in model/KASForm.ts:49*

___
<a id="reporttype"></a>

###  reportType

**● reportType**: *`number`* = 0

*Defined in model/KASForm.ts:46*

___
<a id="title"></a>

###  title

**● title**: *`string`* = ""

*Defined in model/KASForm.ts:16*

___
<a id="type"></a>

###  type

**● type**: *`number`* = 20

*Defined in model/KASForm.ts:43*

___
<a id="version"></a>

###  version

**● version**: *`number`* = 2

*Defined in model/KASForm.ts:25*

___
<a id="visibility"></a>

###  visibility

**● visibility**: *[KASFormResultVisibility](../enums/kasclient.kasformresultvisibility.md)* =  KASFormResultVisibility.All

*Defined in model/KASForm.ts:28*

___

## Methods

<a id="getapicompatiblevisibilitytype"></a>

###  getAPICompatibleVisibilityType

▸ **getAPICompatibleVisibilityType**(visibilityType: *[KASFormResultVisibility](../enums/kasclient.kasformresultvisibility.md)*): `string`

*Defined in model/KASForm.ts:137*

**Parameters:**

| Name | Type |
| ------ | ------ |
| visibilityType | [KASFormResultVisibility](../enums/kasclient.kasformresultvisibility.md) |

**Returns:** `string`

___
<a id="toapicompatiblejson"></a>

###  toAPICompatibleJSON

▸ **toAPICompatibleJSON**(): `JSON`

*Defined in model/KASForm.ts:108*

**Returns:** `JSON`

___
<a id="toclientjson"></a>

###  toClientJSON

▸ **toClientJSON**(): `JSON`

*Defined in model/KASForm.ts:68*

**Returns:** `JSON`

___
<a id="tojson"></a>

###  toJSON

▸ **toJSON**(): `JSON`

*Defined in model/KASForm.ts:59*

**Returns:** `JSON`

___
<a id="addresponsenotificationforaddrow"></a>

### `<Static>` addResponseNotificationForAddRow

▸ **addResponseNotificationForAddRow**(form: *[KASForm](kasclient.kasform.md)*, notificationSpec: *[KASFormResponseNotificationModel](kasclient.kasformresponsenotificationmodel.md)*): `void`

*Defined in model/KASForm.ts:244*

**Parameters:**

| Name | Type |
| ------ | ------ |
| form | [KASForm](kasclient.kasform.md) |
| notificationSpec | [KASFormResponseNotificationModel](kasclient.kasformresponsenotificationmodel.md) |

**Returns:** `void`

___
<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`JSON`*): [KASForm](kasclient.kasform.md)

*Defined in model/KASForm.ts:153*

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `JSON` |

**Returns:** [KASForm](kasclient.kasform.md)

___

