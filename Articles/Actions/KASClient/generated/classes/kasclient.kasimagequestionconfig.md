[type-doc](../README.md) > [KASClient](../modules/kasclient.md) > [KASImageQuestionConfig](../classes/kasclient.kasimagequestionconfig.md)

# Class: KASImageQuestionConfig

## Hierarchy

 [KASQuestionConfig](kasclient.kasquestionconfig.md)

**↳ KASImageQuestionConfig**

## Index

### Properties

* [defaultCameraFilterMode](kasclient.kasimagequestionconfig.md#defaultcamerafiltermode)
* [imageSource](kasclient.kasimagequestionconfig.md#imagesource)
* [pageBreakEnabled](kasclient.kasimagequestionconfig.md#pagebreakenabled)
* [DEFAULT_CAMERA_FILTER_MODE](kasclient.kasimagequestionconfig.md#default_camera_filter_mode)
* [IMAGE_SOURCE_KEY](kasclient.kasimagequestionconfig.md#image_source_key)

### Methods

* [toJSON](kasclient.kasimagequestionconfig.md#tojson)
* [fromJSON](kasclient.kasimagequestionconfig.md#fromjson)

---

## Properties

<a id="defaultcamerafiltermode"></a>

###  defaultCameraFilterMode

**● defaultCameraFilterMode**: *[CameraFilterMode](../enums/kasclient.camerafiltermode.md)* =  CameraFilterMode.Photo

*Defined in model/KASImageQuestionConfig.ts:29*

___
<a id="imagesource"></a>

###  imageSource

**● imageSource**: *[ImagePickerSource](../enums/kasclient.imagepickersource.md)* =  ImagePickerSource.All

*Defined in model/KASImageQuestionConfig.ts:27*

___
<a id="pagebreakenabled"></a>

###  pageBreakEnabled

**● pageBreakEnabled**: *`boolean`* = true

*Inherited from [KASQuestionConfig](kasclient.kasquestionconfig.md).[pageBreakEnabled](kasclient.kasquestionconfig.md#pagebreakenabled)*

*Defined in model/KASQuestionConfig.ts:5*

___
<a id="default_camera_filter_mode"></a>

### `<Static>` DEFAULT_CAMERA_FILTER_MODE

**● DEFAULT_CAMERA_FILTER_MODE**: *`string`* = "dcfm"

*Defined in model/KASImageQuestionConfig.ts:28*

___
<a id="image_source_key"></a>

### `<Static>` IMAGE_SOURCE_KEY

**● IMAGE_SOURCE_KEY**: *`string`* = "is"

*Defined in model/KASImageQuestionConfig.ts:26*

___

## Methods

<a id="tojson"></a>

###  toJSON

▸ **toJSON**(): `JSON`

*Overrides [KASQuestionConfig](kasclient.kasquestionconfig.md).[toJSON](kasclient.kasquestionconfig.md#tojson)*

*Defined in model/KASImageQuestionConfig.ts:31*

**Returns:** `JSON`

___
<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*): [KASImageQuestionConfig](kasclient.kasimagequestionconfig.md)

*Overrides [KASQuestionConfig](kasclient.kasquestionconfig.md).[fromJSON](kasclient.kasquestionconfig.md#fromjson)*

*Defined in model/KASImageQuestionConfig.ts:39*

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASImageQuestionConfig](kasclient.kasimagequestionconfig.md)

___

