[](../README.md) > [KASClient](../modules/kasclient.md) > [KASFormSummaryForGroup](../classes/kasclient.kasformsummaryforgroup.md)

# Class: KASFormSummaryForGroup

## Hierarchy

**KASFormSummaryForGroup**

## Index

### Properties

* [cursor](kasclient.kasformsummaryforgroup.md#cursor)
* [directMemberResponses](kasclient.kasformsummaryforgroup.md#directmemberresponses)
* [responderCount](kasclient.kasformsummaryforgroup.md#respondercount)
* [subgroupSummary](kasclient.kasformsummaryforgroup.md#subgroupsummary)
* [targetCount](kasclient.kasformsummaryforgroup.md#targetcount)


### Methods

* [fromJSON](kasclient.kasformsummaryforgroup.md#fromjson)




---

## Properties

<a id="cursor"></a>

###  cursor

**● cursor**: *`string`* = ""

___




<a id="directmemberresponses"></a>

###  directMemberResponses

**● directMemberResponses**: *`KASActionInstanceResponse`[]* =  []


Sample summary for group

{ "c": "125955414", "rdc": 3, "rs": \[ { "id": "5a1d8f15-79b8-4cd5-a497-a5caff979b74", "n": "ABC", "rid": "0a228aee-c5c0-4dc5-bca0-42a634474e2b@1", "rs": { "0": "Jbbl", "1": "1540980866017", "2": "{"lt":0,"lg":0,"acc":0,"n":"","ty":0}" } }, { "id": "41e589cf-ad48-46b9-9290-786bf64cd599", "n": "SRK", "rid": "13dfa760-df77-4c88-a9f6-f34a76136439@1", "rs": { "0": "Gnuk", "1": "1540981299094", "2": "{"lt":0,"lg":0,"acc":0,"n":"","ty":0}" } } \], "sgs": { "0c6207fc-39ce-4b74-b420-db2d52f2cd08@1": { "n": null, "rdc": 1, "tc": 6 } }, "tc": 6 }


___




<a id="respondercount"></a>

###  responderCount

**● responderCount**: *`number`* = 0

___




<a id="subgroupsummary"></a>

###  subgroupSummary

**● subgroupSummary**: *`object`*

#### Type declaration

___




<a id="targetcount"></a>

###  targetCount

**● targetCount**: *`number`* = 0

___





## Methods

<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*): [KASFormSummaryForGroup](kasclient.kasformsummaryforgroup.md)

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASFormSummaryForGroup](kasclient.kasformsummaryforgroup.md)

___





