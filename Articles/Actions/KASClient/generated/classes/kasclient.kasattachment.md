[](../README.md) > [KASClient](../modules/kasclient.md) > [KASAttachment](../classes/kasclient.kasattachment.md)

# Class: KASAttachment

## Hierarchy

**KASAttachment**

↳  [KASAudioAttachment](kasclient.kasaudioattachment.md)

↳  [KASImageAttachment](kasclient.kasimageattachment.md)

↳  [KASVideoAttachment](kasclient.kasvideoattachment.md)

## Index

### Properties

* [attachmentId](kasclient.kasattachment.md#attachmentid)
* [fileName](kasclient.kasattachment.md#filename)
* [hasSetThumbnail](kasclient.kasattachment.md#hassetthumbnail)
* [localPath](kasclient.kasattachment.md#localpath)
* [requireHighResThumbnail](kasclient.kasattachment.md#requirehighresthumbnail)
* [serverPath](kasclient.kasattachment.md#serverpath)
* [size](kasclient.kasattachment.md#size)
* [thumbnail](kasclient.kasattachment.md#thumbnail)
* [type](kasclient.kasattachment.md#type)


### Methods

* [toJSON](kasclient.kasattachment.md#tojson)
* [fromJSON](kasclient.kasattachment.md#fromjson)
* [hasLocalPath](kasclient.kasattachment.md#haslocalpath)
* [hasServerPath](kasclient.kasattachment.md#hasserverpath)
* [populateModelFromJSON](kasclient.kasattachment.md#populatemodelfromjson)




---

## Properties

<a id="attachmentid"></a>

###  attachmentId

**● attachmentId**: *`string`* = ""

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


The following string keys("ty", "afn", "asb", etc.) MUST be in sync with the Attachment object model representation in iOS and Android code. This is vital for proper serialization and deserialization over the KAS bridge.


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

▸ **populateModelFromJSON**(attachment: *[KASAttachment](kasclient.kasattachment.md)*, object: *`JSON`*): `void`

**Parameters:**

| Name | Type |
| ------ | ------ |
| attachment | [KASAttachment](kasclient.kasattachment.md) |
| object | `JSON` |

**Returns:** `void`

___





