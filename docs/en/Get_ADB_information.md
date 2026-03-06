API Description
---------------

Retrieve ADB Information

Request URL
-----------

* `https://openapi.geelark.com/open/v1/adb/getData`

Request Method
--------------

* POST

Request Parameters
------------------

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| ids | Yes | array\[string\] | Array of cloud phone IDs | \["526209711930868736"\] |

Request Example
---------------

```json
{
 "ids" : ["526806961778328576","524798337208026112","524783756767134720"]
}
```


Response Data Description
-------------------------
### items
| Parameter Name | Type | Description |
| --- | --- | --- |
| code | int | Error code: 0 indicates success; for other codes, refer to the error code table |
| id | string | Cloud phone ID |
| ip | string | Connection IP |
| port | string | Port |
| pwd | string | Password |

Response Example
----------------

```json
{
    "traceId": "8AB9D6B482B679ECB5578314903B80B9",
    "code": 0,
    "msg": "success",
    "data": {
        "items": [
            {
                "code": 0,
                "id": "524783756767134720",
                "ip": "124.71.210.176",
                "pwd": "8c1da4",
                "port": "25219"
            },
            {
                "code": 42002,
                "id": "524798337208026112",
                "ip": "",
                "pwd": "",
                "port": ""
            }
        ]
    }
}
```

Error Codes
-----------

The following are specific error codes for this API. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 42001 | Cloud phone does not exist |
| 42002 | Cloud phone is not running |
| 49001 | ADB is not enabled |
| 49002 | The device does not support ADB |