## /media
API end-point to send media attachments to conversation groups inside Kaizala.

Supported file formats are:

||||
|---|---|---|
| Images | .jpg, .jpeg, .png |
| Audio Files | .mp3, .wav |
| Documents | .doc, .docx, .xls, .xlsx, .ppt, .pptx, .pdf |

Posting media attachments to Kaizala is a two step process. First, you will need to upload the media file to a repository using the /media endpoint and then use the resource URL later to post as an Action inside Kaizala.

Corresponding content-type(mime type) needs to be set in content header of the media file. Without this api will throw unsupported Media(415) error. 

### POST /media

    POST https://{api_root}/media

##### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| HTTP Header | applicationId | String | No | ID associated with the Connector that was registered by the developer – on behalf of which the API calls need to be made |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |
| HTTP Header | Content-Type | String | No | To indicate that a file is being uploaded. value: multipart/form-data |

##### Request body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| POST Body | files | Media file to be uploaded in a multipart/form-data format |

##### Response body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| mediaResource | String | Encoded media data to be used in subsequent send action calls |

### POST /groups/{groupId}

You can get additional details about a specific resource member (a group here) by specifying the identifier as a URL path parameter.

    GET https://{api_root}/groups/{groupId}/actions

##### Request Parameters

|  | Parameter | Type | Optional? | Description |
| :---: | :---: | :---: | :---:	| :--- |
| URL Path Parameter | groupId | String | No | GUID representing the groupId of the specific group resource |
| HTTP Header | applicationId | String | No | ID associated with the Connector that was registered by the developer – on behalf of which the API calls need to be made |
| HTTP Header | accessToken | String | No | Access Token received from the auth end-point |
| HTTP Header | Content-Type | String | No | value: application/json |

##### Request body

| Parameter | Type | Description |
| :---: | :---: | :--- |
| actionType | String | Id of the Kaizala Action to send. Please refer to the table above for supported Actions and their respective IDs. |
| actionBody | JSON Object | Object representing data needed for the respective Action. Parameters defined below for each of the supported MediaType. |

###### actionBody for media files

| Parameter | Type | Optional? | Description |
| :---: | :---: | :---:	| :--- |
| MediaResource | String | No | MediaResource string from a previous call to /media where you need to upload the attachment |
| Caption | String | Yes | Text String that is shown alongwith the media file as a part of the message |


###### Sample JSON Response

```javascript
{
    "referenceId": "6007fe3a-cb7c-4eef-bb88-934273aabc1e"
}
```


