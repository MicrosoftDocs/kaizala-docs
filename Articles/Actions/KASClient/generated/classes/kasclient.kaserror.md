[](../README.md) > [KASClient](../modules/kasclient.md) > [KASError](../classes/kasclient.kaserror.md)

# Class: KASError

## Hierarchy

**KASError**

## Index

### Constructors

* [constructor](kasclient.kaserror.md#constructor)
  ### Properties

* [description](kasclient.kaserror.md#description)
* [errorCode](kasclient.kaserror.md#errorcode)
  ### Methods

* [toString](kasclient.kaserror.md#tostring)
* [fromErrorString](kasclient.kaserror.md#fromerrorstring)
* [fromString](kasclient.kaserror.md#fromstring)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new KASError**(errorCode: *[KASErrorCode](../enums/kasclient.kaserrorcode.md)*, description: *`string`*): [KASError](kasclient.kaserror.md)

**Parameters:**

| Name | Type |
| ------ | ------ |
| errorCode | [KASErrorCode](../enums/kasclient.kaserrorcode.md) |
| description | `string` |

**Returns:** [KASError](kasclient.kaserror.md)

___

## Properties

<a id="description"></a>

###  description

**● description**: *`String`* = ""

___
<a id="errorcode"></a>

###  errorCode

**● errorCode**: *[KASErrorCode](../enums/kasclient.kaserrorcode.md)* =  KASErrorCode.NONE

___

## Methods

<a id="tostring"></a>

###  toString

▸ **toString**(): `string`

**Returns:** `string`

___
<a id="fromerrorstring"></a>

### `<Static>` fromErrorString

▸ **fromErrorString**(stringifyError: *`string`*): [KASError](kasclient.kaserror.md)

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| stringifyError | `string` |  stringified dictionary of error with code and description |

**Returns:** [KASError](kasclient.kaserror.md)
returns KASError object made from stringified error. For null string, null object is returned.

___
<a id="fromstring"></a>

### `<Static>` fromString

▸ **fromString**(stringifyError: *`string`*): [KASError](kasclient.kaserror.md)

**Parameters:**

| Name | Type | Description |
| ------ | ------ | ------ |
| stringifyError | `string` |  stringified dictionary of error with code and description |

**Returns:** [KASError](kasclient.kaserror.md)
returns KASError object made from stringified error. For null string also,
         non-null error code is returned

___

