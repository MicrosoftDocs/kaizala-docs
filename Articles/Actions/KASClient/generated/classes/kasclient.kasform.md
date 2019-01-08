[](../README.md) > [KASClient](../modules/kasclient.md) > [KASForm](../classes/kasclient.kasform.md)

# Class: KASForm

## Hierarchy

**KASForm**

## Index

---

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

___
<a id="conversationid"></a>

###  conversationId

**● conversationId**: *`string`* = ""

___
<a id="creatorid"></a>

###  creatorId

**● creatorId**: *`string`* = ""

___
<a id="expiry"></a>

###  expiry

**● expiry**: *`number`* = 0

___
<a id="id"></a>

###  id

**● id**: *`string`* = ""

___
<a id="isanonymous"></a>

###  isAnonymous

**● isAnonymous**: *`boolean`* = false

___
<a id="isgrouplevelaggregationrequired"></a>

###  isGroupLevelAggregationRequired

**● isGroupLevelAggregationRequired**: *`boolean`* = false

___
<a id="islocationrequested"></a>

###  isLocationRequested

**● isLocationRequested**: *`boolean`* = false

___
<a id="isresponseappended"></a>

###  isResponseAppended

**● isResponseAppended**: *`boolean`* = false

___
<a id="json"></a>

###  json

**● json**: *`JSON`*

___
<a id="packageid"></a>

###  packageId

**● packageId**: *`string`* = ""

___
<a id="properties"></a>

###  properties

**● properties**: *[KASFormProperty](kasclient.kasformproperty.md)[]* =  []

___
<a id="questions"></a>

###  questions

**● questions**: *[KASQuestion](kasclient.kasquestion.md)[]* =  []

___
<a id="reporttype"></a>

###  reportType

**● reportType**: *`number`* = 0

___
<a id="title"></a>

###  title

**● title**: *`string`* = ""

___
<a id="type"></a>

###  type

**● type**: *`number`* = 20

___
<a id="version"></a>

###  version

**● version**: *`number`* = 2

___
<a id="visibility"></a>

###  visibility

**● visibility**: *[KASFormResultVisibility](../enums/kasclient.kasformresultvisibility.md)* =  KASFormResultVisibility.All

___

## Methods

<a id="getapicompatiblevisibilitytype"></a>

###  getAPICompatibleVisibilityType

▸ **getAPICompatibleVisibilityType**(visibilityType: *[KASFormResultVisibility](../enums/kasclient.kasformresultvisibility.md)*): `string`

**Parameters:**

| Name | Type |
| ------ | ------ |
| visibilityType | [KASFormResultVisibility](../enums/kasclient.kasformresultvisibility.md) |

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
<a id="addresponsenotificationforaddrow"></a>

### `<Static>` addResponseNotificationForAddRow

▸ **addResponseNotificationForAddRow**(form: *[KASForm](kasclient.kasform.md)*, notificationSpec: *[KASFormResponseNotificationModel](kasclient.kasformresponsenotificationmodel.md)*): `void`

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

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `JSON` |

**Returns:** [KASForm](kasclient.kasform.md)

___

