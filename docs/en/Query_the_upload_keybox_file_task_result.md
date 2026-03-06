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
    "taskId": "528715748189668352"
}
```

Response Example
----------------


```json
{
    "traceId": "A62BBBF3A294487F9B49B9FFA0F84CA8",
    "code": 0,
    "msg": "success",
	"data": {
        "status": 1
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

