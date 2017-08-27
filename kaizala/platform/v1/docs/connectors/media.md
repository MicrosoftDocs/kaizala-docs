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
| mediaId | String | Media Id to be used in subsequent send action calls |
| mediaResource | String | Encoded media data to be used in subsequent send action calls |

