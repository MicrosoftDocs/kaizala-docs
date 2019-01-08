[type-doc](../README.md) > [KASClient](../modules/kasclient.md) > [KASAttachment](../classes/kasclient.kasattachment.md)

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

*Defined in model/KASAttachment.ts:8*

___
<a id="filename"></a>

###  fileName

**● fileName**: *`string`* = ""

*Defined in model/KASAttachment.ts:4*

___
<a id="hassetthumbnail"></a>

###  hasSetThumbnail

**● hasSetThumbnail**: *`boolean`* = false

*Defined in model/KASAttachment.ts:10*

___
<a id="localpath"></a>

###  localPath

**● localPath**: *`string`* = ""

*Defined in model/KASAttachment.ts:6*

___
<a id="requirehighresthumbnail"></a>

###  requireHighResThumbnail

**● requireHighResThumbnail**: *`boolean`* = false

*Defined in model/KASAttachment.ts:12*

___
<a id="serverpath"></a>

###  serverPath

**● serverPath**: *`string`* = ""

*Defined in model/KASAttachment.ts:7*

___
<a id="size"></a>

###  size

**● size**: *`number`* = 0

*Defined in model/KASAttachment.ts:5*

___
<a id="thumbnail"></a>

###  thumbnail

**● thumbnail**: *`string`* = ""

*Defined in model/KASAttachment.ts:11*

___
<a id="type"></a>

###  type

**● type**: *[KASAttachmentType](../enums/kasclient.kasattachmenttype.md)* =  KASAttachmentType.Image

*Defined in model/KASAttachment.ts:3*

___

## Methods

<a id="tojson"></a>

###  toJSON

▸ **toJSON**(): `JSON`

*Defined in model/KASAttachment.ts:18*

The following string keys("ty", "afn", "asb", etc.) MUST be in sync with the Attachment object model representation in iOS and Android code. This is vital for proper serialization and deserialization over the KAS bridge.

**Returns:** `JSON`

___
<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*): [KASAttachment](kasclient.kasattachment.md)

*Defined in model/KASAttachment.ts:34*

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASAttachment](kasclient.kasattachment.md)

___
<a id="haslocalpath"></a>

### `<Static>` hasLocalPath

▸ **hasLocalPath**(obj: *[KASAttachment](kasclient.kasattachment.md)*): `boolean`

*Defined in model/KASAttachment.ts:86*

**Parameters:**

| Name | Type |
| ------ | ------ |
| obj | [KASAttachment](kasclient.kasattachment.md) |

**Returns:** `boolean`

___
<a id="hasserverpath"></a>

### `<Static>` hasServerPath

▸ **hasServerPath**(obj: *[KASAttachment](kasclient.kasattachment.md)*): `boolean`

*Defined in model/KASAttachment.ts:90*

**Parameters:**

| Name | Type |
| ------ | ------ |
| obj | [KASAttachment](kasclient.kasattachment.md) |

**Returns:** `boolean`

___
<a id="populatemodelfromjson"></a>

### `<Static>` populateModelFromJSON

▸ **populateModelFromJSON**(attachment: *[KASAttachment](kasclient.kasattachment.md)*, object: *`JSON`*): `void`

*Defined in model/KASAttachment.ts:44*

**Parameters:**

| Name | Type |
| ------ | ------ |
| attachment | [KASAttachment](kasclient.kasattachment.md) |
| object | `JSON` |

**Returns:** `void`

___

