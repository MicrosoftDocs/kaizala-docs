[](../README.md) > [KASClient](../modules/kasclient.md) > [KASFormResponse](../classes/kasclient.kasformresponse.md)

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


Group id


___




<a id="groupname"></a>

###  groupName

**● groupName**: *`string`* = ""


Group Name


___




<a id="id"></a>

###  id

**● id**: *`string`* = ""


A unique response id, required in case of updating an existing response


___




<a id="questiontoanswermap"></a>

###  questionToAnswerMap

**● questionToAnswerMap**: *`object`*


A map of question id to answer Dictionary<QuestionId: number, Answer: string>

#### Type declaration

___




<a id="responderid"></a>

###  responderId

**● responderId**: *`string`* = ""


Responder id


___




<a id="respondername"></a>

###  responderName

**● responderName**: *`string`* = ""


Responder name


___




<a id="sendstatus"></a>

###  sendStatus

**● sendStatus**: *[KASFormMessageSendStatus](../enums/kasclient.kasformmessagesendstatus.md)* =  KASFormMessageSendStatus.Unknown


Response message send status


___




<a id="sendtime"></a>

###  sendTime

**● sendTime**: *`number`* = 0


Response send time


___




<a id="servertolocalasseturlmap"></a>

###  serverToLocalAssetUrlMap

**● serverToLocalAssetUrlMap**: *`object`*


A map for serverUrl against localUrl of all the image attachments to a response Dictionary<ServerUrl: string, LocalUrl: string>

#### Type declaration

___





## Methods

<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*): [KASFormResponse](kasclient.kasformresponse.md)

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASFormResponse](kasclient.kasformresponse.md)

___





