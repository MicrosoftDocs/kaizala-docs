[](../README.md) > [KASClient](../modules/kasclient.md) > [KASFormInfoRequest](../classes/kasclient.kasforminforequest.md)

# Class: KASFormInfoRequest

This encapsulates the request for KASClient.Form.fetchFormInfosAsync api. This api is used to fetch Action instance (or form) infos for an Action pacakge
## Hierarchy

**KASFormInfoRequest**

## Index

### Properties

* [creatorId](kasclient.kasforminforequest.md#creatorid)
* [cursor](kasclient.kasforminforequest.md#cursor)
* [packageId](kasclient.kasforminforequest.md#packageid)
* [scopeId](kasclient.kasforminforequest.md#scopeid)

---

## Properties

<a id="creatorid"></a>

###  creatorId

**● creatorId**: *`string`* = ""

Action instance (or form) creator id - optional field

___
<a id="cursor"></a>

###  cursor

**● cursor**: *`string`* = ""

Cursor to fetch responses in batch

___
<a id="packageid"></a>

###  packageId

**● packageId**: *`string`* = ""

Action package id whose instances need to be fetched

___
<a id="scopeid"></a>

###  scopeId

**● scopeId**: *`string`* = ""

Scope id - group id for Single/Group scope, tenant id for Tenant scope, user id for User scope

___

