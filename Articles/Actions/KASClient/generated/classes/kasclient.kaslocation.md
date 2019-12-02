[](../README.md) > [KASClient](../modules/kasclient.md) > [KASLocation](../classes/kasclient.kaslocation.md)

# Class: KASLocation

## Hierarchy

**KASLocation**

## Index

### Properties

* [latitude](kasclient.kaslocation.md#latitude)
* [longitude](kasclient.kaslocation.md#longitude)
* [placeAddress](kasclient.kaslocation.md#placeaddress)
* [placeName](kasclient.kaslocation.md#placename)
  ### Methods

* [isEmpty](kasclient.kaslocation.md#isempty)
* [isEqual](kasclient.kaslocation.md#isequal)
* [toJSON](kasclient.kaslocation.md#tojson)
* [fromJSON](kasclient.kaslocation.md#fromjson)

---

## Properties

<a id="latitude"></a>

###  latitude

**● latitude**: *`number`* = 0

Latitude of the location

___
<a id="longitude"></a>

###  longitude

**● longitude**: *`number`* = 0

Longitude of the location

___
<a id="placeaddress"></a>

###  placeAddress

**● placeAddress**: *`string`* = ""

Address of the location

___
<a id="placename"></a>

###  placeName

**● placeName**: *`string`* = ""

Name of the location

___

## Methods

<a id="isempty"></a>

###  isEmpty

▸ **isEmpty**(): `boolean`

**Returns:** `boolean`

___
<a id="isequal"></a>

###  isEqual

▸ **isEqual**(location: *[KASLocation](kasclient.kaslocation.md)*): `boolean`

**Parameters:**

| Name | Type |
| ------ | ------ |
| location | [KASLocation](kasclient.kaslocation.md) |

**Returns:** `boolean`

___
<a id="tojson"></a>

###  toJSON

▸ **toJSON**(): `JSON`

**Returns:** `JSON`

___
<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`JSON`*): [KASLocation](kasclient.kaslocation.md)

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `JSON` |

**Returns:** [KASLocation](kasclient.kaslocation.md)

___

