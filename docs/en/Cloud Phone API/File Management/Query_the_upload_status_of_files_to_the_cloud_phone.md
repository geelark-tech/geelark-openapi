[TOC]

API Description
---------------

Query the upload status of files to the cloud phone.  
You can actively retrieve the result within one hour of initiating the upload task; after expiration, the retrieval will fail.

Request URL
-----------

*   `https://openapi.geelark.com/open/v1/phone/uploadFile/result`

Request Method
--------------

*   POST

Request Parameters
------------------

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| taskId | Yes | string | Task ID | Refer to request example |

Request Example
---------------
```json
{
    &quot;taskId&quot;: &quot;528715748189668352&quot;
}
```

Response Example
----------------


```json
{
    &quot;traceId&quot;: &quot;A62BBBF3A294487F9B49B9FFA0F84CA8&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
	&quot;data&quot;: {
        &quot;status&quot;: 1
    }
}
```

Response Data Description
-------------------------

| Parameter Name | Type | Description |
| --- | --- | --- |
| status | int | 0: Failed to retrieve; 1: Uploading; 2: Upload successful; 3: Upload failed |

Error Codes
-----------

For error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).
