[type-doc](../README.md) > [KASClient](../modules/kasclient.md) > [KASFormProperty](../classes/kasclient.kasformproperty.md)

# Class: KASFormProperty

## Hierarchy

**KASFormProperty**

## Index

### Properties

* [name](kasclient.kasformproperty.md#name)
* [type](kasclient.kasformproperty.md#type)
* [value](kasclient.kasformproperty.md#value)

### Methods

* [getAPICompatiblePropertyType](kasclient.kasformproperty.md#getapicompatiblepropertytype)
* [toAPICompatibleJSON](kasclient.kasformproperty.md#toapicompatiblejson)
* [toClientJSON](kasclient.kasformproperty.md#toclientjson)
* [toJSON](kasclient.kasformproperty.md#tojson)
* [fromJSON](kasclient.kasformproperty.md#fromjson)

---

## Properties

<a id="name"></a>

###  name

**● name**: *`string`* = ""

*Defined in model/KASFormProperty.ts:4*

___
<a id="type"></a>

###  type

**● type**: *[KASFormPropertyType](../enums/kasclient.kasformpropertytype.md)* =  KASFormPropertyType.Text

*Defined in model/KASFormProperty.ts:7*

___
<a id="value"></a>

###  value

**● value**: *`string`* = ""

*Defined in model/KASFormProperty.ts:10*

___

## Methods

<a id="getapicompatiblepropertytype"></a>

###  getAPICompatiblePropertyType

▸ **getAPICompatiblePropertyType**(type: *`string`*): `string`

*Defined in model/KASFormProperty.ts:12*

**Parameters:**

| Name | Type |
| ------ | ------ |
| type | `string` |

**Returns:** `string`

___
<a id="toapicompatiblejson"></a>

###  toAPICompatibleJSON

▸ **toAPICompatibleJSON**(): `JSON`

*Defined in model/KASFormProperty.ts:41*

**Returns:** `JSON`

___
<a id="toclientjson"></a>

###  toClientJSON

▸ **toClientJSON**(): `JSON`

*Defined in model/KASFormProperty.ts:33*

**Returns:** `JSON`

___
<a id="tojson"></a>

###  toJSON

▸ **toJSON**(): `JSON`

*Defined in model/KASFormProperty.ts:24*

**Returns:** `JSON`

___
<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`JSON`*): [KASFormProperty](kasclient.kasformproperty.md)

*Defined in model/KASFormProperty.ts:49*

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `JSON` |

**Returns:** [KASFormProperty](kasclient.kasformproperty.md)

___

