[type-doc](../README.md) > [KASClient](../modules/kasclient.md) > [KASConversationDetails](../classes/kasclient.kasconversationdetails.md)

# Class: KASConversationDetails

Defines details of host and source conversation

## Hierarchy

**KASConversationDetails**

## Index

### Properties

* [currentUserId](kasclient.kasconversationdetails.md#currentuserid)
* [currentUserRoleInHostConversation](kasclient.kasconversationdetails.md#currentuserroleinhostconversation)
* [hostConversationId](kasclient.kasconversationdetails.md#hostconversationid)
* [hostConversationParticipantsMap](kasclient.kasconversationdetails.md#hostconversationparticipantsmap)
* [hostConversationTitle](kasclient.kasconversationdetails.md#hostconversationtitle)
* [hostConversationType](kasclient.kasconversationdetails.md#hostconversationtype)
* [sourceConversationId](kasclient.kasconversationdetails.md#sourceconversationid)
* [sourceConversationTitle](kasclient.kasconversationdetails.md#sourceconversationtitle)
* [sourceConversationType](kasclient.kasconversationdetails.md#sourceconversationtype)

### Methods

* [fromJSON](kasclient.kasconversationdetails.md#fromjson)

---

## Properties

<a id="currentuserid"></a>

###  currentUserId

**● currentUserId**: *`string`* = ""

*Defined in model/KASConversationDetails.ts:30*

___
<a id="currentuserroleinhostconversation"></a>

###  currentUserRoleInHostConversation

**● currentUserRoleInHostConversation**: *[KASParticipantRole](../enums/kasclient.kasparticipantrole.md)* =  KASParticipantRole.NONE

*Defined in model/KASConversationDetails.ts:33*

___
<a id="hostconversationid"></a>

###  hostConversationId

**● hostConversationId**: *`string`* = ""

*Defined in model/KASConversationDetails.ts:8*

___
<a id="hostconversationparticipantsmap"></a>

###  hostConversationParticipantsMap

**● hostConversationParticipantsMap**: *`object`*

*Defined in model/KASConversationDetails.ts:18*

#### Type declaration

___
<a id="hostconversationtitle"></a>

###  hostConversationTitle

**● hostConversationTitle**: *`string`* = ""

*Defined in model/KASConversationDetails.ts:11*

___
<a id="hostconversationtype"></a>

###  hostConversationType

**● hostConversationType**: *[KASFormConversationType](../enums/kasclient.kasformconversationtype.md)* =  KASFormConversationType.NONE

*Defined in model/KASConversationDetails.ts:14*

___
<a id="sourceconversationid"></a>

###  sourceConversationId

**● sourceConversationId**: *`string`* = ""

*Defined in model/KASConversationDetails.ts:21*

___
<a id="sourceconversationtitle"></a>

###  sourceConversationTitle

**● sourceConversationTitle**: *`string`* = ""

*Defined in model/KASConversationDetails.ts:24*

___
<a id="sourceconversationtype"></a>

###  sourceConversationType

**● sourceConversationType**: *[KASFormConversationType](../enums/kasclient.kasformconversationtype.md)* =  KASFormConversationType.NONE

*Defined in model/KASConversationDetails.ts:27*

___

## Methods

<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*): [KASConversationDetails](kasclient.kasconversationdetails.md)

*Defined in model/KASConversationDetails.ts:35*

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASConversationDetails](kasclient.kasconversationdetails.md)

___

