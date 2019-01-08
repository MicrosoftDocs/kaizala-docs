[type-doc](../README.md) > [KASClient](../modules/kasclient.md) > [KASPhoneNumber](../classes/kasclient.kasphonenumber.md)

# Class: KASPhoneNumber

## Hierarchy

**KASPhoneNumber**

## Index

### Constructors

* [constructor](kasclient.kasphonenumber.md#constructor)

### Properties

* [countryPhoneCode](kasclient.kasphonenumber.md#countryphonecode)
* [phoneNumber](kasclient.kasphonenumber.md#phonenumber)

### Methods

* [toJSON](kasclient.kasphonenumber.md#tojson)
* [toString](kasclient.kasphonenumber.md#tostring)
* [fromJSON](kasclient.kasphonenumber.md#fromjson)

---

## Constructors

<a id="constructor"></a>

###  constructor

⊕ **new KASPhoneNumber**(countryPhoneCode?: *`number`*, phoneNumber?: *`string`*): [KASPhoneNumber](kasclient.kasphonenumber.md)

*Defined in model/KASPhoneNumber.ts:4*

**Parameters:**

| Name | Type | Default value |
| ------ | ------ | ------ |
| `Default value` countryPhoneCode | `number` | 0 |
| `Default value` phoneNumber | `string` | &quot;&quot; |

**Returns:** [KASPhoneNumber](kasclient.kasphonenumber.md)

___

## Properties

<a id="countryphonecode"></a>

###  countryPhoneCode

**● countryPhoneCode**: *`number`* = 0

*Defined in model/KASPhoneNumber.ts:3*

___
<a id="phonenumber"></a>

###  phoneNumber

**● phoneNumber**: *`string`* = ""

*Defined in model/KASPhoneNumber.ts:4*

___

## Methods

<a id="tojson"></a>

###  toJSON

▸ **toJSON**(): `JSON`

*Defined in model/KASPhoneNumber.ts:25*

**Returns:** `JSON`

___
<a id="tostring"></a>

###  toString

▸ **toString**(): `string`

*Defined in model/KASPhoneNumber.ts:32*

**Returns:** `string`

___
<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(phoneNumberReponseJSON: *`any`*): [KASPhoneNumber](kasclient.kasphonenumber.md)

*Defined in model/KASPhoneNumber.ts:11*

**Parameters:**

| Name | Type |
| ------ | ------ |
| phoneNumberReponseJSON | `any` |

**Returns:** [KASPhoneNumber](kasclient.kasphonenumber.md)

___

