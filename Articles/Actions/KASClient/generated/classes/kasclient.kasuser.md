[](../README.md) > [KASClient](../modules/kasclient.md) > [KASUser](../classes/kasclient.kasuser.md)

# Class: KASUser

## Hierarchy

**KASUser**

## Index

### Properties

* [id](kasclient.kasuser.md#id)
* [name](kasclient.kasuser.md#name)
* [originalName](kasclient.kasuser.md#originalname)
* [phoneNumber](kasclient.kasuser.md#phonenumber)
* [pictureBGColor](kasclient.kasuser.md#picturebgcolor)
* [pictureInitials](kasclient.kasuser.md#pictureinitials)
* [pictureUrl](kasclient.kasuser.md#pictureurl)


### Methods

* [fromJSON](kasclient.kasuser.md#fromjson)




---

## Properties

<a id="id"></a>

###  id

**● id**: *`string`* = ""


Unique user id


___




<a id="name"></a>

###  name

**● name**: *`string`* = ""


Name of the user ("You" for the current user)


___




<a id="originalname"></a>

###  originalName

**● originalName**: *`string`* = ""


Not considering "You"


___




<a id="phonenumber"></a>

###  phoneNumber

**● phoneNumber**: *`string`* = ""


Phone number of the user


___




<a id="picturebgcolor"></a>

###  pictureBGColor

**● pictureBGColor**: *`string`* = ""


In case the PictureUrl is not there, we should use the users initials as the profile pic, below two members are for that


___




<a id="pictureinitials"></a>

###  pictureInitials

**● pictureInitials**: *`string`* = ""

___




<a id="pictureurl"></a>

###  pictureUrl

**● pictureUrl**: *`string`* = ""


Profile picture url of the user


___





## Methods

<a id="fromjson"></a>

### `<Static>` fromJSON

▸ **fromJSON**(object: *`JSON`*): [KASUser](kasclient.kasuser.md)

**Parameters:**

| Name | Type |
| ------ | ------ |
| object | `JSON` |

**Returns:** [KASUser](kasclient.kasuser.md)

___





