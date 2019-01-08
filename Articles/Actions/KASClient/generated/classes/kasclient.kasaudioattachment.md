[type-doc](../README.md) > [KASClient](../modules/kasclient.md) > [KASAudioAttachment](../classes/kasclient.kasaudioattachment.md)

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

*Inherited from [KASAttachment](kasclient.kasattachment.md).[attachmentId](kasclient.kasattachment.md#attachmentid)*

*Defined in model/KASAttachment.ts:8*

___
<a id="duration"></a>

###  duration

**● duration**: *`number`* = 0

*Defined in model/KASAudioAttachment.ts:3*

___
<a id="filename"></a>

###  fileName

**● fileName**: *`string`* = ""

*Inherited from [KASAttachment](kasclient.kasattachment.md).[fileName](kasclient.kasattachment.md#filename)*

*Defined in model/KASAttachment.ts:4*

___
<a id="hassetthumbnail"></a>

###  hasSetThumbnail

**● hasSetThumbnail**: *`boolean`* = false

*Inherited from [KASAttachment](kasclient.kasattachment.md).[hasSetThumbnail](kasclient.kasattachment.md#hassetthumbnail)*

*Defined in model/KASAttachment.ts:10*

___
<a id="localpath"></a>

###  localPath

**● localPath**: *`string`* = ""

*Inherited from [KASAttachment](kasclient.kasattachment.md).[localPath](kasclient.kasattachment.md#localpath)*

*Defined in model/KASAttachment.ts:6*

___
<a id="requirehighresthumbnail"></a>

###  requireHighResThumbnail

**● requireHighResThumbnail**: *`boolean`* = false

*Inherited from [KASAttachment](kasclient.kasattachment.md).[requireHighResThumbnail](kasclient.kasattachment.md#requirehighresthumbnail)*

*Defined in model/KASAttachment.ts:12*

___
<a id="serverpath"></a>

###  serverPath

**● serverPath**: *`string`* = ""

*Inherited from [KASAttachment](kasclient.kasattachment.md).[serverPath](kasclient.kasattachment.md#serverpath)*

*Defined in model/KASAttachment.ts:7*

___
<a id="size"></a>

###  size

**● size**: *`number`* = 0

*Inherited from [KASAttachment](kasclient.kasattachment.md).[size](kasclient.kasattachment.md#size)*

*Defined in model/KASAttachment.ts:5*

___
<a id="thumbnail"></a>

###  thumbnail

**● thumbnail**: *`string`* = ""

*Inherited from [KASAttachment](kasclient.kasattachment.md).[thumbnail](kasclient.kasattachment.md#thumbnail)*

*Defined in model/KASAttachment.ts:11*

___
<a id="type"></a>

###  type

**● type**: *[KASAttachmentType](../enums/kasclient.kasattachmenttype.md)* =  KASAttachmentType.Image

*Inherited from [KASAttachment](kasclient.kasattachment.md).[type](kasclient.kasattachment.md#type)*

*Defined in model/KASAttachment.ts:3*

___

## Methods

<a id="tojson"></a>

###  toJSON

▸ **toJSON**(): `JSON`

*Overrides [KASAttachment](kasclient.kasattachment.md).[toJSON](kasclient.kasattachment.md#tojson)*

*Defined in model/KASAudioAttachment.ts:5*

**Returns:** `JSON`

___
<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*): [KASAttachment](kasclient.kasattachment.md)

*Overrides [KASAttachment](kasclient.kasattachment.md).[fromJSON](kasclient.kasattachment.md#fromjson)*

*Defined in model/KASAudioAttachment.ts:11*

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASAttachment](kasclient.kasattachment.md)

___
<a id="haslocalpath"></a>

### `<Static>` hasLocalPath

▸ **hasLocalPath**(obj: *[KASAttachment](kasclient.kasattachment.md)*): `boolean`

*Inherited from [KASAttachment](kasclient.kasattachment.md).[hasLocalPath](kasclient.kasattachment.md#haslocalpath)*

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

*Inherited from [KASAttachment](kasclient.kasattachment.md).[hasServerPath](kasclient.kasattachment.md#hasserverpath)*

*Defined in model/KASAttachment.ts:90*

**Parameters:**

| Name | Type |
| ------ | ------ |
| obj | [KASAttachment](kasclient.kasattachment.md) |

**Returns:** `boolean`

___
<a id="populatemodelfromjson"></a>

### `<Static>` populateModelFromJSON

▸ **populateModelFromJSON**(attachment: *[KASAudioAttachment](kasclient.kasaudioattachment.md)*, object: *`JSON`*): `void`

*Overrides [KASAttachment](kasclient.kasattachment.md).[populateModelFromJSON](kasclient.kasattachment.md#populatemodelfromjson)*

*Defined in model/KASAudioAttachment.ts:21*

**Parameters:**

| Name | Type |
| ------ | ------ |
| attachment | [KASAudioAttachment](kasclient.kasaudioattachment.md) |
| object | `JSON` |

**Returns:** `void`

___

