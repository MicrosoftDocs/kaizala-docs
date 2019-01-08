[type-doc](../README.md) > [KASClient](../modules/kasclient.md) > [KASFormResponseNotificationModel](../classes/kasclient.kasformresponsenotificationmodel.md)

# Class: KASFormResponseNotificationModel

## Hierarchy

**KASFormResponseNotificationModel**

## Index

### Constructors

* [constructor](kasclient.kasformresponsenotificationmodel.md#constructor)

### Properties

* [messagePreview](kasclient.kasformresponsenotificationmodel.md#messagepreview)
* [messageTarget](kasclient.kasformresponsenotificationmodel.md#messagetarget)
* [pushTarget](kasclient.kasformresponsenotificationmodel.md#pushtarget)

### Methods

* [toJSON](kasclient.kasformresponsenotificationmodel.md#tojson)
* [fromJson](kasclient.kasformresponsenotificationmodel.md#fromjson)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new KASFormResponseNotificationModel**(messageTarget?: *[KASFormResponseNotificationTarget](../enums/kasclient.kasformresponsenotificationtarget.md)[]*, pushTarget?: *[KASFormResponseNotificationTarget](../enums/kasclient.kasformresponsenotificationtarget.md)[]*, messagePreview?: *`String`*): [KASFormResponseNotificationModel](kasclient.kasformresponsenotificationmodel.md)

*Defined in model/KASFormResponseNotificationModel.ts:12*

**Parameters:**

| Name | Type | Default value |
| ------ | ------ | ------ |
| `Default value` messageTarget | [KASFormResponseNotificationTarget](../enums/kasclient.kasformresponsenotificationtarget.md)[] |  null |
| `Default value` pushTarget | [KASFormResponseNotificationTarget](../enums/kasclient.kasformresponsenotificationtarget.md)[] |  null |
| `Default value` messagePreview | `String` |  null |

**Returns:** [KASFormResponseNotificationModel](kasclient.kasformresponsenotificationmodel.md)

___

## Properties

<a id="messagepreview"></a>

###  messagePreview

**● messagePreview**: *`String`* = ""

*Defined in model/KASFormResponseNotificationModel.ts:12*

___
<a id="messagetarget"></a>

###  messageTarget

**● messageTarget**: *[KASFormResponseNotificationTarget](../enums/kasclient.kasformresponsenotificationtarget.md)[]*

*Defined in model/KASFormResponseNotificationModel.ts:10*

___
<a id="pushtarget"></a>

###  pushTarget

**● pushTarget**: *[KASFormResponseNotificationTarget](../enums/kasclient.kasformresponsenotificationtarget.md)[]*

*Defined in model/KASFormResponseNotificationModel.ts:11*

___

## Methods

<a id="tojson"></a>

###  toJSON

▸ **toJSON**(): `JSON`

*Defined in model/KASFormResponseNotificationModel.ts:42*

**Returns:** `JSON`

___
<a id="fromjson"></a>

### `<Static>` fromJson

▸ **fromJson**(object: *`JSON`*): [KASFormResponseNotificationModel](kasclient.kasformresponsenotificationmodel.md)

*Defined in model/KASFormResponseNotificationModel.ts:20*

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `JSON` |

**Returns:** [KASFormResponseNotificationModel](kasclient.kasformresponsenotificationmodel.md)

___

