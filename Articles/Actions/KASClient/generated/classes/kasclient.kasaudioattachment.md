[](../README.md) > [KASClient](../modules/kasclient.md) > [KASAudioAttachment](../classes/kasclient.kasaudioattachment.md)

# Class: KASAudioAttachment

## Hierarchy

 [KASAttachment](kasclient.kasattachment.md)

**↳ KASAudioAttachment**

## Index

### Properties

* [attachmentId](kasclient.kasaudioattachment.md#attachmentid)
* [duration](kasclient.kasaudioattachment.md#duration)
* [fileName](kasclient.kasaudioattachment.md#filename)
* [hasSetThumbnail](kasclient.kasaudioattachment.md#hassetthumbnail)
* [localPath](kasclient.kasaudioattachment.md#localpath)
* [requireHighResThumbnail](kasclient.kasaudioattachment.md#requirehighresthumbnail)
* [serverPath](kasclient.kasaudioattachment.md#serverpath)
* [size](kasclient.kasaudioattachment.md#size)
* [thumbnail](kasclient.kasaudioattachment.md#thumbnail)
* [type](kasclient.kasaudioattachment.md#type)


### Methods

* [toJSON](kasclient.kasaudioattachment.md#tojson)
* [fromJSON](kasclient.kasaudioattachment.md#fromjson)
* [hasLocalPath](kasclient.kasaudioattachment.md#haslocalpath)
* [hasServerPath](kasclient.kasaudioattachment.md#hasserverpath)
* [populateModelFromJSON](kasclient.kasaudioattachment.md#populatemodelfromjson)




---

## Properties

<a id="attachmentid"></a>

###  attachmentId

**● attachmentId**: *`string`* = ""

___




<a id="duration"></a>

###  duration

**● duration**: *`number`* = 0

___




<a id="filename"></a>

###  fileName

**● fileName**: *`string`* = ""

___




<a id="hassetthumbnail"></a>

###  hasSetThumbnail

**● hasSetThumbnail**: *`boolean`* = false

___




<a id="localpath"></a>

###  localPath

**● localPath**: *`string`* = ""

___




<a id="requirehighresthumbnail"></a>

###  requireHighResThumbnail

**● requireHighResThumbnail**: *`boolean`* = false

___




<a id="serverpath"></a>

###  serverPath

**● serverPath**: *`string`* = ""

___




<a id="size"></a>

###  size

**● size**: *`number`* = 0

___




<a id="thumbnail"></a>

###  thumbnail

**● thumbnail**: *`string`* = ""

___




<a id="type"></a>

###  type

**● type**: *[KASAttachmentType](../enums/kasclient.kasattachmenttype.md)* =  KASAttachmentType.Image

___





## Methods

<a id="tojson"></a>

###  toJSON

▸ **toJSON**(): `JSON`

**Returns:** `JSON`

___




<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*): [KASAttachment](kasclient.kasattachment.md)

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASAttachment](kasclient.kasattachment.md)

___




<a id="haslocalpath"></a>

### `<Static>` hasLocalPath

▸ **hasLocalPath**(obj: *[KASAttachment](kasclient.kasattachment.md)*): `boolean`

**Parameters:**

| Name | Type |
| ------ | ------ |
| obj | [KASAttachment](kasclient.kasattachment.md) |

**Returns:** `boolean`

___




<a id="hasserverpath"></a>

### `<Static>` hasServerPath

▸ **hasServerPath**(obj: *[KASAttachment](kasclient.kasattachment.md)*): `boolean`

**Parameters:**

| Name | Type |
| ------ | ------ |
| obj | [KASAttachment](kasclient.kasattachment.md) |

**Returns:** `boolean`

___




<a id="populatemodelfromjson"></a>

### `<Static>` populateModelFromJSON

▸ **populateModelFromJSON**(attachment: *[KASAudioAttachment](kasclient.kasaudioattachment.md)*, object: *`JSON`*): `void`

**Parameters:**

| Name | Type |
| ------ | ------ |
| attachment | [KASAudioAttachment](kasclient.kasaudioattachment.md) |
| object | `JSON` |

**Returns:** `void`

___





