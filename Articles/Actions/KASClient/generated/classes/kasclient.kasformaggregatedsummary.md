[type-doc](../README.md) > [KASClient](../modules/kasclient.md) > [KASFormAggregatedSummary](../classes/kasclient.kasformaggregatedsummary.md)

# Class: KASFormAggregatedSummary

## Hierarchy

**KASFormAggregatedSummary**

## Index

### Properties

* [formId](kasclient.kasformaggregatedsummary.md#formid)
* [formStatus](kasclient.kasformaggregatedsummary.md#formstatus)
* [json](kasclient.kasformaggregatedsummary.md#json)
* [result](kasclient.kasformaggregatedsummary.md#result)
* [targetResponderCount](kasclient.kasformaggregatedsummary.md#targetrespondercount)
* [totalParticipantsCount](kasclient.kasformaggregatedsummary.md#totalparticipantscount)
* [totalResponseCount](kasclient.kasformaggregatedsummary.md#totalresponsecount)

### Methods

* [fromJSON](kasclient.kasformaggregatedsummary.md#fromjson)

---

## Properties

<a id="formid"></a>

###  formId

**● formId**: *`string`* = ""

*Defined in model/KASFormAggregatedSummary.ts:11*

___
<a id="formstatus"></a>

###  formStatus

**● formStatus**: *[FormStatus](../enums/kasclient.formstatus.md)* =  FormStatus.Active

*Defined in model/KASFormAggregatedSummary.ts:13*

___
<a id="json"></a>

###  json

**● json**: *`JSON`*

*Defined in model/KASFormAggregatedSummary.ts:26*

___
<a id="result"></a>

###  result

**● result**: *`any`[]* =  []

*Defined in model/KASFormAggregatedSummary.ts:24*

___
<a id="targetrespondercount"></a>

###  targetResponderCount

**● targetResponderCount**: *`number`* = 0

*Defined in model/KASFormAggregatedSummary.ts:22*

___
<a id="totalparticipantscount"></a>

###  totalParticipantsCount

**● totalParticipantsCount**: *`number`* = 0

*Defined in model/KASFormAggregatedSummary.ts:19*

___
<a id="totalresponsecount"></a>

###  totalResponseCount

**● totalResponseCount**: *`number`* = 0

*Defined in model/KASFormAggregatedSummary.ts:16*

___

## Methods

<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`JSON`*, questions: *[KASQuestion](kasclient.kasquestion.md)[]*): [KASFormAggregatedSummary](kasclient.kasformaggregatedsummary.md)

*Defined in model/KASFormAggregatedSummary.ts:45*

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `JSON` |
| questions | [KASQuestion](kasclient.kasquestion.md)[] |

**Returns:** [KASFormAggregatedSummary](kasclient.kasformaggregatedsummary.md)

___

