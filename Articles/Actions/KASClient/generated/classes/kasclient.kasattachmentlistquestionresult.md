[type-doc](../README.md) > [KASClient](../modules/kasclient.md) > [KASAttachmentListQuestionResult](../classes/kasclient.kasattachmentlistquestionresult.md)

# Class: KASAttachmentListQuestionResult

This model contains data for every response to an Attachment List Type question.

## Hierarchy

 [KASQuestionResult](kasclient.kasquestionresult.md)

**↳ KASAttachmentListQuestionResult**

## Index

### Properties

* [attachmentListType](kasclient.kasattachmentlistquestionresult.md#attachmentlisttype)
* [attachmentsResponseJSONStrings](kasclient.kasattachmentlistquestionresult.md#attachmentsresponsejsonstrings)
* [questionId](kasclient.kasattachmentlistquestionresult.md#questionid)
* [questionTitle](kasclient.kasattachmentlistquestionresult.md#questiontitle)
* [questionType](kasclient.kasattachmentlistquestionresult.md#questiontype)
* [timeStamps](kasclient.kasattachmentlistquestionresult.md#timestamps)
* [userInfo](kasclient.kasattachmentlistquestionresult.md#userinfo)

### Methods

* [fromJSON](kasclient.kasattachmentlistquestionresult.md#fromjson)

---

## Properties

<a id="attachmentlisttype"></a>

###  attachmentListType

**● attachmentListType**: *[AttachmentListResponseType](../enums/kasclient.attachmentlistresponsetype.md)* =  AttachmentListResponseType.GENERIC

*Defined in model/KASAttachmentListQuestionResult.ts:13*

attachmentListType: contains the type of the attachment list response

___
<a id="attachmentsresponsejsonstrings"></a>

###  attachmentsResponseJSONStrings

**● attachmentsResponseJSONStrings**: *`string`[]* =  []

*Defined in model/KASAttachmentListQuestionResult.ts:32*

attachmentsResponseJSONStrings: contains the list of attachments corresponding to every response as a JSON string which is directly available in the questionIdToAnswerMap.

___
<a id="questionid"></a>

###  questionId

**● questionId**: *`number`* = 0

*Inherited from [KASQuestionResult](kasclient.kasquestionresult.md).[questionId](kasclient.kasquestionresult.md#questionid)*

*Defined in model/KASQuestionResult.ts:10*

___
<a id="questiontitle"></a>

###  questionTitle

**● questionTitle**: *`string`* = ""

*Inherited from [KASQuestionResult](kasclient.kasquestionresult.md).[questionTitle](kasclient.kasquestionresult.md#questiontitle)*

*Defined in model/KASQuestionResult.ts:4*

___
<a id="questiontype"></a>

###  questionType

**● questionType**: *[KASQuestionType](../enums/kasclient.kasquestiontype.md)* =  KASQuestionType.None

*Inherited from [KASQuestionResult](kasclient.kasquestionresult.md).[questionType](kasclient.kasquestionresult.md#questiontype)*

*Defined in model/KASQuestionResult.ts:7*

___
<a id="timestamps"></a>

###  timeStamps

**● timeStamps**: *`string`[]* =  []

*Defined in model/KASAttachmentListQuestionResult.ts:25*

timeStamps: contains the response timestamps for every response.

___
<a id="userinfo"></a>

###  userInfo

**● userInfo**: *[KASUser](kasclient.kasuser.md)[]* =  []

*Defined in model/KASAttachmentListQuestionResult.ts:20*

userInfo: contains instances of KASUser with details for the respondent for the particular response so that we can show the name and profile picture of the respondent.

___

## Methods

<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`any`*): [KASQuestionResult](kasclient.kasquestionresult.md)

*Inherited from [KASQuestionResult](kasclient.kasquestionresult.md).[fromJSON](kasclient.kasquestionresult.md#fromjson)*

*Defined in model/KASQuestionResult.ts:12*

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `any` |

**Returns:** [KASQuestionResult](kasclient.kasquestionresult.md)

___

