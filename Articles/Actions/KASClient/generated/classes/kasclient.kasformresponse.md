[type-doc](../README.md) > [KASClient](../modules/kasclient.md) > [KASFormResponse](../classes/kasclient.kasformresponse.md)

# Class: KASFormResponse

## Hierarchy

**KASFormResponse**

## Index

### Properties

* [groupId](kasclient.kasformresponse.md#groupid)
* [groupName](kasclient.kasformresponse.md#groupname)
* [id](kasclient.kasformresponse.md#id)
* [questionToAnswerMap](kasclient.kasformresponse.md#questiontoanswermap)
* [responderId](kasclient.kasformresponse.md#responderid)
* [responderName](kasclient.kasformresponse.md#respondername)
* [sendStatus](kasclient.kasformresponse.md#sendstatus)
* [sendTime](kasclient.kasformresponse.md#sendtime)
* [serverToLocalAssetUrlMap](kasclient.kasformresponse.md#servertolocalasseturlmap)

### Methods

* [fromJSON](kasclient.kasformresponse.md#fromjson)

---

## Properties

<a id="groupid"></a>

###  groupId

**● groupId**: *`string`* = ""

*Defined in model/KASFormResponse.ts:21*

___
<a id="groupname"></a>

###  groupName

**● groupName**: *`string`* = ""

*Defined in model/KASFormResponse.ts:24*

___
<a id="id"></a>

###  id

**● id**: *`string`* = ""

*Defined in model/KASFormResponse.ts:4*

___
<a id="questiontoanswermap"></a>

###  questionToAnswerMap

**● questionToAnswerMap**: *`object`*

*Defined in model/KASFormResponse.ts:18*

#### Type declaration

___
<a id="responderid"></a>

###  responderId

**● responderId**: *`string`* = ""

*Defined in model/KASFormResponse.ts:27*

___
<a id="respondername"></a>

###  responderName

**● responderName**: *`string`* = ""

*Defined in model/KASFormResponse.ts:30*

___
<a id="sendstatus"></a>

###  sendStatus

**● sendStatus**: *[KASFormMessageSendStatus](../enums/kasclient.kasformmessagesendstatus.md)* =  KASFormMessageSendStatus.Unknown

*Defined in model/KASFormResponse.ts:7*

___
<a id="sendtime"></a>

###  sendTime

**● sendTime**: *`number`* = 0

*Defined in model/KASFormResponse.ts:10*

___
<a id="servertolocalasseturlmap"></a>

###  serverToLocalAssetUrlMap

**● serverToLocalAssetUrlMap**: *`object`*

*Defined in model/KASFormResponse.ts:14*

#### Type declaration

___

## Methods

<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*): [KASFormResponse](kasclient.kasformresponse.md)

*Defined in model/KASFormResponse.ts:32*

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASFormResponse](kasclient.kasformresponse.md)

___

