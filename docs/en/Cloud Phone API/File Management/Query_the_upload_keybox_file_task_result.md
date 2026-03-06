[TOC]

API Description
---------------

After calling the upload Keybox file interface, get the execution result through the returned taskId

Request URL
-----------

*   `https://openapi.geelark.com/open/v1/phone/keyboxUpload/result`

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
| status | int |  0: Uploading; 1: Upload successful; 2: Upload failed |

Error Codes
-----------

For error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

