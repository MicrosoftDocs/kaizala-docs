[](../README.md) > [KASClient](../modules/kasclient.md) > [KASImageAttachment](../classes/kasclient.kasimageattachment.md)

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

▸ **fromJSON**(object: *`any`*): [KASImageAttachment](kasclient.kasimageattachment.md)

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASImageAttachment](kasclient.kasimageattachment.md)

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

▸ **populateModelFromJSON**(attachment: *[KASImageAttachment](kasclient.kasimageattachment.md)*, object: *`JSON`*): `void`

**Parameters:**

| Name | Type |
| ------ | ------ |
| attachment | [KASImageAttachment](kasclient.kasimageattachment.md) |
| object | `JSON` |

**Returns:** `void`

___





