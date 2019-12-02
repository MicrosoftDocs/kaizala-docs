[](../README.md) > [KASClient](../modules/kasclient.md) > [KASActionLocalCacheProp](../classes/kasclient.kasactionlocalcacheprop.md)

# Class: KASActionLocalCacheProp

## Hierarchy

**KASActionLocalCacheProp**

## Index

### Properties

* [cacheScope](kasclient.kasactionlocalcacheprop.md#cachescope)
* [cacheVisibility](kasclient.kasactionlocalcacheprop.md#cachevisibility)
* [key](kasclient.kasactionlocalcacheprop.md#key)
* [value](kasclient.kasactionlocalcacheprop.md#value)
  ### Methods

* [toJSON](kasclient.kasactionlocalcacheprop.md#tojson)
* [fromJSON](kasclient.kasactionlocalcacheprop.md#fromjson)

---

## Properties

<a id="cachescope"></a>

###  cacheScope

**● cacheScope**: *[CacheScope](../enums/kasclient.cachescope.md)* =  CacheScope.Global

cacheScope indicates the data will store at global or converastion level.

___
<a id="cachevisibility"></a>

###  cacheVisibility

**● cacheVisibility**: *[CacheVisibility](../enums/kasclient.cachevisibility.md)* =  CacheVisibility.App

cacheVisibility indicates that the data visible to other app or not.

___
<a id="key"></a>

###  key

**● key**: *`string`* = ""

key of the value stored in cache

___
<a id="value"></a>

###  value

**● value**: *`string`* = ""

___

## Methods

<a id="tojson"></a>

###  toJSON

▸ **toJSON**(): `JSON`

**Returns:** `JSON`

___
<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`JSON`*): [KASActionLocalCacheProp](kasclient.kasactionlocalcacheprop.md)

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `JSON` |

**Returns:** [KASActionLocalCacheProp](kasclient.kasactionlocalcacheprop.md)

___

