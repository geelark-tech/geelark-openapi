API Description
---------------

Upload files to the cloud phone.  
Before uploading, please start the cloud phone. The file will be uploaded to the "Downloads" folder of the cloud phone.

Request URL
-----------

*   `https://openapi.geelark.com/open/v1/phone/uploadFile`

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
    "id": "528715748189668352",
	"fileUrl" : "https://material-prod.geelark.cn/app/icon/20240506/nFrUEcRc9I.jpg"
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
        "taskId": "1850726441252569088"
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

Callback Result and Example
---------------------------

Please refer to Callback Example