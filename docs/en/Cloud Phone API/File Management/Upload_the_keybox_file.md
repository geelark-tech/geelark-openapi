[TOC]

API Description
---------------

Upload the keybox file and pass Google&#039;s integrity verification. This is currently only supported on Android 12/13/15. For Android 12/13, simply upload the keybox file. Android 15 requires the following additional steps:
1. Update Google Play and GMS to the latest version.
2. Log in with a valid Google account.
3. Download the Play Integrity API Checker from Google Play.

Request URL
-----------

*   `https://openapi.geelark.com/open/v1/phone/keyboxUpload`

Request Method
--------------

*   POST

Request Parameters
------------------

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | Cloud phone ID | Refer to request example |
| fileUrl | Yes | string | File URL | Refer to request example |

Request Example
---------------
```json
{
    &quot;id&quot;: &quot;528715748189668352&quot;,
	&quot;fileUrl&quot;:&quot;https://material.geelark.cn/client-img/oakendn.xml&quot;
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
        &quot;taskId&quot;: &quot;1850726441252569088&quot;
    }
}
```
Response Data Description
-------------------------

| Parameter Name | Type | Description |
| --- | --- | --- |
| taskId | string | Task ID |

Error Codes
-----------

The following are specific error codes for this API. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 42001 | Cloud phone does not exist |
| 42002 | Cloud phone is not running |
| 43026  | Cloud phone system not support             |
| 60003  | Invalid file url                |

Callback Result and Example
---------------------------

Please refer to Callback Example

