[](../README.md) > [KASClient](../modules/kasclient.md) > [KASForm](../classes/kasclient.kasform.md)

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

Who can send reminder, default value is sender

___

<a id="conversationid"></a>

###  conversationId

**● conversationId**: *`string`* = ""

Associated conversation id, shouldn't be changed

___

<a id="creatorid"></a>

###  creatorId

**● creatorId**: *`string`* = ""

User id who created the form, shouldn't be changed

___

<a id="expiry"></a>

###  expiry

**● expiry**: *`number`* = 0

Expiry time of the form

___

<a id="id"></a>

###  id

**● id**: *`string`* = ""

Form id, shouldn't be changed

___

<a id="isanonymous"></a>

###  isAnonymous

**● isAnonymous**: *`boolean`* = false

If the form is anonymous, default is false

___

<a id="isgrouplevelaggregationrequired"></a>

###  isGroupLevelAggregationRequired

**● isGroupLevelAggregationRequired**: *`boolean`* = false

whether server should do subgroup level aggregation on results for this action instance

___

<a id="islocationrequested"></a>

###  isLocationRequested

**● isLocationRequested**: *`boolean`* = false

Denotes if participants' location is attached with the response or not, default is false

___

<a id="isresponseappended"></a>

###  isResponseAppended

**● isResponseAppended**: *`boolean`* = false

Denotes if multiple responses from a user are allowed or not, default is false

___

<a id="json"></a>

###  json

**● json**: *`JSON`*

___

<a id="packageid"></a>

###  packageId

**● packageId**: *`string`* = ""

Package id of the MiniApp, shouldn't be changed

___

<a id="properties"></a>

###  properties

**● properties**: *[KASFormProperty](kasclient.kasformproperty.md)[]* =  []

A list of metadata associated with the form

___

<a id="questions"></a>

###  questions

**● questions**: *[KASQuestion](kasclient.kasquestion.md)[]* =  []

All the questions associated with the form

___

<a id="reporttype"></a>

###  reportType

**● reportType**: *`number`* = 0

Report Type of survey, default is 0, for job it should be 1

___

<a id="title"></a>

###  title

**● title**: *`string`* = ""

Form title

___

<a id="type"></a>

###  type

**● type**: *`number`* = 20

Type of the form, default is 20, shouldn't be changed

___

<a id="version"></a>

###  version

**● version**: *`number`* = 2

Version of the form, default value is 2, shouldn't be changed

___

<a id="visibility"></a>

###  visibility

**● visibility**: *[KASFormResultVisibility](../enums/kasclient.kasformresultvisibility.md)* =  KASFormResultVisibility.All

Who can see the summary of the form, default value is All

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

