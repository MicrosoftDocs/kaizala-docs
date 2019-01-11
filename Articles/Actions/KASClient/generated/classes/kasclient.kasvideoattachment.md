[](../README.md) > [KASClient](../modules/kasclient.md) > [KASVideoAttachment](../classes/kasclient.kasvideoattachment.md)

# Class: KASVideoAttachment

## Hierarchy

 [KASAttachment](kasclient.kasattachment.md)

**↳ KASVideoAttachment**

## Index

### Properties

* [attachmentId](kasclient.kasvideoattachment.md#attachmentid)
* [duration](kasclient.kasvideoattachment.md#duration)
* [fileName](kasclient.kasvideoattachment.md#filename)
* [hasSetThumbnail](kasclient.kasvideoattachment.md#hassetthumbnail)
* [localPath](kasclient.kasvideoattachment.md#localpath)
* [requireHighResThumbnail](kasclient.kasvideoattachment.md#requirehighresthumbnail)
* [serverPath](kasclient.kasvideoattachment.md#serverpath)
* [size](kasclient.kasvideoattachment.md#size)
* [streamingPath](kasclient.kasvideoattachment.md#streamingpath)
* [thumbnail](kasclient.kasvideoattachment.md#thumbnail)
* [type](kasclient.kasvideoattachment.md#type)


### Methods

* [toJSON](kasclient.kasvideoattachment.md#tojson)
* [fromJSON](kasclient.kasvideoattachment.md#fromjson)
* [hasLocalPath](kasclient.kasvideoattachment.md#haslocalpath)
* [hasServerPath](kasclient.kasvideoattachment.md#hasserverpath)
* [populateModelFromJSON](kasclient.kasvideoattachment.md#populatemodelfromjson)




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




<a id="streamingpath"></a>

###  streamingPath

**● streamingPath**: *`string`* = ""

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

▸ **populateModelFromJSON**(attachment: *[KASVideoAttachment](kasclient.kasvideoattachment.md)*, object: *`JSON`*): `void`

**Parameters:**

| Name | Type |
| ------ | ------ |
| attachment | [KASVideoAttachment](kasclient.kasvideoattachment.md) |
| object | `JSON` |

**Returns:** `void`

___





