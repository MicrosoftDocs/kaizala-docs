[type-doc](../README.md) > [KASClient](../modules/kasclient.md) > [KASAttachmentListQuestionConfig](../classes/kasclient.kasattachmentlistquestionconfig.md)

# Class: KASAttachmentListQuestionConfig

## Hierarchy

 [KASQuestionConfig](kasclient.kasquestionconfig.md)

**↳ KASAttachmentListQuestionConfig**

## Index

### Properties

* [attachmentListType](kasclient.kasattachmentlistquestionconfig.md#attachmentlisttype)
* [defaultCameraFilterMode](kasclient.kasattachmentlistquestionconfig.md#defaultcamerafiltermode)
* [imageSource](kasclient.kasattachmentlistquestionconfig.md#imagesource)
* [maxImageCount](kasclient.kasattachmentlistquestionconfig.md#maximagecount)
* [pageBreakEnabled](kasclient.kasattachmentlistquestionconfig.md#pagebreakenabled)
* [ATTACHMENT_LIST_TYPE](kasclient.kasattachmentlistquestionconfig.md#attachment_list_type)
* [DEFAULT_CAMERA_FILTER_MODE](kasclient.kasattachmentlistquestionconfig.md#default_camera_filter_mode)
* [IMAGE_SOURCE_KEY](kasclient.kasattachmentlistquestionconfig.md#image_source_key)
* [MAX_IMAGE_COUNT_KEY](kasclient.kasattachmentlistquestionconfig.md#max_image_count_key)

### Methods

* [toJSON](kasclient.kasattachmentlistquestionconfig.md#tojson)
* [fromJSON](kasclient.kasattachmentlistquestionconfig.md#fromjson)

---

## Properties

<a id="attachmentlisttype"></a>

###  attachmentListType

**● attachmentListType**: *[AttachmentListResponseType](../enums/kasclient.attachmentlistresponsetype.md)* =  AttachmentListResponseType.GENERIC

*Defined in model/KASAttachmentListQuestionConfig.ts:18*

___
<a id="defaultcamerafiltermode"></a>

###  defaultCameraFilterMode

**● defaultCameraFilterMode**: *[CameraFilterMode](../enums/kasclient.camerafiltermode.md)* =  CameraFilterMode.Photo

*Defined in model/KASAttachmentListQuestionConfig.ts:19*

___
<a id="imagesource"></a>

###  imageSource

**● imageSource**: *[ImagePickerSource](../enums/kasclient.imagepickersource.md)* =  ImagePickerSource.All

*Defined in model/KASAttachmentListQuestionConfig.ts:16*

___
<a id="maximagecount"></a>

###  maxImageCount

**● maxImageCount**: *`number`* = 10

*Defined in model/KASAttachmentListQuestionConfig.ts:17*

___
<a id="pagebreakenabled"></a>

###  pageBreakEnabled

**● pageBreakEnabled**: *`boolean`* = true

*Inherited from [KASQuestionConfig](kasclient.kasquestionconfig.md).[pageBreakEnabled](kasclient.kasquestionconfig.md#pagebreakenabled)*

*Defined in model/KASQuestionConfig.ts:5*

___
<a id="attachment_list_type"></a>

### `<Static>` ATTACHMENT_LIST_TYPE

**● ATTACHMENT_LIST_TYPE**: *`string`* = "alt"

*Defined in model/KASAttachmentListQuestionConfig.ts:14*

___
<a id="default_camera_filter_mode"></a>

### `<Static>` DEFAULT_CAMERA_FILTER_MODE

**● DEFAULT_CAMERA_FILTER_MODE**: *`string`* = "dcfm"

*Defined in model/KASAttachmentListQuestionConfig.ts:15*

___
<a id="image_source_key"></a>

### `<Static>` IMAGE_SOURCE_KEY

**● IMAGE_SOURCE_KEY**: *`string`* = "is"

*Defined in model/KASAttachmentListQuestionConfig.ts:13*

___
<a id="max_image_count_key"></a>

### `<Static>` MAX_IMAGE_COUNT_KEY

**● MAX_IMAGE_COUNT_KEY**: *`string`* = "mic"

*Defined in model/KASAttachmentListQuestionConfig.ts:12*

___

## Methods

<a id="tojson"></a>

###  toJSON

▸ **toJSON**(): `JSON`

*Overrides [KASQuestionConfig](kasclient.kasquestionconfig.md).[toJSON](kasclient.kasquestionconfig.md#tojson)*

*Defined in model/KASAttachmentListQuestionConfig.ts:21*

**Returns:** `JSON`

___
<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*): [KASAttachmentListQuestionConfig](kasclient.kasattachmentlistquestionconfig.md)

*Overrides [KASQuestionConfig](kasclient.kasquestionconfig.md).[fromJSON](kasclient.kasquestionconfig.md#fromjson)*

*Defined in model/KASAttachmentListQuestionConfig.ts:31*

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASAttachmentListQuestionConfig](kasclient.kasattachmentlistquestionconfig.md)

___

