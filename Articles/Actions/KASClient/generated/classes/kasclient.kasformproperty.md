[](../README.md) > [KASClient](../modules/kasclient.md) > [KASFormProperty](../classes/kasclient.kasformproperty.md)

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


Name of the metadata


___




<a id="type"></a>

###  type

**● type**: *[KASFormPropertyType](../enums/kasclient.kasformpropertytype.md)* =  KASFormPropertyType.Text


Type of the metadata


___




<a id="value"></a>

###  value

**● value**: *`string`* = ""


Value of the metadata


___





## Methods

<a id="getapicompatiblepropertytype"></a>

###  getAPICompatiblePropertyType

▸ **getAPICompatiblePropertyType**(type: *`string`*): `string`

**Parameters:**

| Name | Type |
| ------ | ------ |
| type | `string` |

**Returns:** `string`

___




<a id="toapicompatiblejson"></a>

###  toAPICompatibleJSON

▸ **toAPICompatibleJSON**(): `JSON`

**Returns:** `JSON`

___




<a id="toclientjson"></a>

###  toClientJSON

▸ **toClientJSON**(): `JSON`

**Returns:** `JSON`

___




<a id="tojson"></a>

###  toJSON

▸ **toJSON**(): `JSON`

**Returns:** `JSON`

___




<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`JSON`*): [KASFormProperty](kasclient.kasformproperty.md)

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `JSON` |

**Returns:** [KASFormProperty](kasclient.kasformproperty.md)

___





