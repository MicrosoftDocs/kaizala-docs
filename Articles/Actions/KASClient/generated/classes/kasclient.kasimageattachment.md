[type-doc](../README.md) > [KASClient](../modules/kasclient.md) > [KASImageAttachment](../classes/kasclient.kasimageattachment.md)

# Class: KASImageAttachment

## Hierarchy

 [KASAttachment](kasclient.kasattachment.md)

**↳ KASImageAttachment**

## Index

### Properties

* [attachmentId](kasclient.kasimageattachment.md#attachmentid)
* [fileName](kasclient.kasimageattachment.md#filename)
* [generateThumbnailServerUrl](kasclient.kasimageattachment.md#generatethumbnailserverurl)
* [hasSetThumbnail](kasclient.kasimageattachment.md#hassetthumbnail)
* [height](kasclient.kasimageattachment.md#height)
* [localPath](kasclient.kasimageattachment.md#localpath)
* [requireHighResThumbnail](kasclient.kasimageattachment.md#requirehighresthumbnail)
* [serverPath](kasclient.kasimageattachment.md#serverpath)
* [size](kasclient.kasimageattachment.md#size)
* [thumbnail](kasclient.kasimageattachment.md#thumbnail)
* [thumbnailServerUrl](kasclient.kasimageattachment.md#thumbnailserverurl)
* [type](kasclient.kasimageattachment.md#type)
* [width](kasclient.kasimageattachment.md#width)

### Methods

* [toJSON](kasclient.kasimageattachment.md#tojson)
* [fromJSON](kasclient.kasimageattachment.md#fromjson)
* [hasLocalPath](kasclient.kasimageattachment.md#haslocalpath)
* [hasServerPath](kasclient.kasimageattachment.md#hasserverpath)
* [populateModelFromJSON](kasclient.kasimageattachment.md#populatemodelfromjson)

---

## Properties

<a id="attachmentid"></a>

###  attachmentId

**● attachmentId**: *`string`* = ""

*Inherited from [KASAttachment](kasclient.kasattachment.md).[attachmentId](kasclient.kasattachment.md#attachmentid)*

*Defined in model/KASAttachment.ts:8*

___
<a id="filename"></a>

###  fileName

**● fileName**: *`string`* = ""

*Inherited from [KASAttachment](kasclient.kasattachment.md).[fileName](kasclient.kasattachment.md#filename)*

*Defined in model/KASAttachment.ts:4*

___
<a id="generatethumbnailserverurl"></a>

###  generateThumbnailServerUrl

**● generateThumbnailServerUrl**: *`boolean`* = false

*Defined in model/KASImageAttachment.ts:3*

___
<a id="hassetthumbnail"></a>

###  hasSetThumbnail

**● hasSetThumbnail**: *`boolean`* = false

*Inherited from [KASAttachment](kasclient.kasattachment.md).[hasSetThumbnail](kasclient.kasattachment.md#hassetthumbnail)*

*Defined in model/KASAttachment.ts:10*

___
<a id="height"></a>

###  height

**● height**: *`number`* = 0

*Defined in model/KASImageAttachment.ts:6*

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
<a id="thumbnailserverurl"></a>

###  thumbnailServerUrl

**● thumbnailServerUrl**: *`string`* = ""

*Defined in model/KASImageAttachment.ts:4*

___
<a id="type"></a>

###  type

**● type**: *[KASAttachmentType](../enums/kasclient.kasattachmenttype.md)* =  KASAttachmentType.Image

*Inherited from [KASAttachment](kasclient.kasattachment.md).[type](kasclient.kasattachment.md#type)*

*Defined in model/KASAttachment.ts:3*

___
<a id="width"></a>

###  width

**● width**: *`number`* = 0

*Defined in model/KASImageAttachment.ts:5*

___

## Methods

<a id="tojson"></a>

###  toJSON

▸ **toJSON**(): `JSON`

*Overrides [KASAttachment](kasclient.kasattachment.md).[toJSON](kasclient.kasattachment.md#tojson)*

*Defined in model/KASImageAttachment.ts:8*

**Returns:** `JSON`

___
<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*): [KASImageAttachment](kasclient.kasimageattachment.md)

*Overrides [KASAttachment](kasclient.kasattachment.md).[fromJSON](kasclient.kasattachment.md#fromjson)*

*Defined in model/KASImageAttachment.ts:17*

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASImageAttachment](kasclient.kasimageattachment.md)

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

▸ **populateModelFromJSON**(attachment: *[KASImageAttachment](kasclient.kasimageattachment.md)*, object: *`JSON`*): `void`

*Overrides [KASAttachment](kasclient.kasattachment.md).[populateModelFromJSON](kasclient.kasattachment.md#populatemodelfromjson)*

*Defined in model/KASImageAttachment.ts:27*

**Parameters:**

| Name | Type |
| ------ | ------ |
| attachment | [KASImageAttachment](kasclient.kasimageattachment.md) |
| object | `JSON` |

**Returns:** `void`

___

