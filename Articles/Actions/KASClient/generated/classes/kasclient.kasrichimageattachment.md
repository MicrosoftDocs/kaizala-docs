[](../README.md) > [KASClient](../modules/kasclient.md) > [KASRichImageAttachment](../classes/kasclient.kasrichimageattachment.md)

# Class: KASRichImageAttachment

## Hierarchy

↳  [KASImageAttachment](kasclient.kasimageattachment.md)

**↳ KASRichImageAttachment**

## Index

### Properties

* [attachmentId](kasclient.kasrichimageattachment.md#attachmentid)
* [fileName](kasclient.kasrichimageattachment.md#filename)
* [generateThumbnailServerUrl](kasclient.kasrichimageattachment.md#generatethumbnailserverurl)
* [hasSetThumbnail](kasclient.kasrichimageattachment.md#hassetthumbnail)
* [height](kasclient.kasrichimageattachment.md#height)
* [id](kasclient.kasrichimageattachment.md#id)
* [localPath](kasclient.kasrichimageattachment.md#localpath)
* [metadataFetchState](kasclient.kasrichimageattachment.md#metadatafetchstate)
* [ocrData](kasclient.kasrichimageattachment.md#ocrdata)
* [processedOCRData](kasclient.kasrichimageattachment.md#processedocrdata)
* [requireHighResThumbnail](kasclient.kasrichimageattachment.md#requirehighresthumbnail)
* [serverPath](kasclient.kasrichimageattachment.md#serverpath)
* [size](kasclient.kasrichimageattachment.md#size)
* [thumbnail](kasclient.kasrichimageattachment.md#thumbnail)
* [thumbnailServerUrl](kasclient.kasrichimageattachment.md#thumbnailserverurl)
* [type](kasclient.kasrichimageattachment.md#type)
* [width](kasclient.kasrichimageattachment.md#width)
### Methods

* [toJSON](kasclient.kasrichimageattachment.md#tojson)
* [fromJSON](kasclient.kasrichimageattachment.md#fromjson)
* [hasLocalPath](kasclient.kasrichimageattachment.md#haslocalpath)
* [hasServerPath](kasclient.kasrichimageattachment.md#hasserverpath)
* [populateModelFromJSON](kasclient.kasrichimageattachment.md#populatemodelfromjson)

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
<a id="generatethumbnailserverurl"></a>

###  generateThumbnailServerUrl

**● generateThumbnailServerUrl**: *`boolean`* = false

___
<a id="hassetthumbnail"></a>

###  hasSetThumbnail

**● hasSetThumbnail**: *`boolean`* = false

___
<a id="height"></a>

###  height

**● height**: *`number`* = 0

___
<a id="id"></a>

###  id

**● id**: *`string`* =  null

___
<a id="localpath"></a>

###  localPath

**● localPath**: *`string`* = ""

___
<a id="metadatafetchstate"></a>

###  metadataFetchState

**● metadataFetchState**: *[ImageMetadataFetchState](../enums/kasclient.imagemetadatafetchstate.md)* =  ImageMetadataFetchState.Initiated

___
<a id="ocrdata"></a>

###  ocrData

**● ocrData**: *`string`* =  null

___
<a id="processedocrdata"></a>

###  processedOCRData

**● processedOCRData**: *`string`* =  null

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
<a id="thumbnailserverurl"></a>

###  thumbnailServerUrl

**● thumbnailServerUrl**: *`string`* = ""

___
<a id="type"></a>

###  type

**● type**: *[KASAttachmentType](../enums/kasclient.kasattachmenttype.md)* =  KASAttachmentType.Image

___
<a id="width"></a>

###  width

**● width**: *`number`* = 0

___

## Methods

<a id="tojson"></a>

###  toJSON

▸ **toJSON**(): `JSON`

**Returns:** `JSON`

___
<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*): [KASRichImageAttachment](kasclient.kasrichimageattachment.md)

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASRichImageAttachment](kasclient.kasrichimageattachment.md)

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

▸ **populateModelFromJSON**(attachment: *[KASRichImageAttachment](kasclient.kasrichimageattachment.md)*, object: *`JSON`*): `void`

**Parameters:**

| Name | Type |
| ------ | ------ |
| attachment | [KASRichImageAttachment](kasclient.kasrichimageattachment.md) |
| object | `JSON` |

**Returns:** `void`

___

