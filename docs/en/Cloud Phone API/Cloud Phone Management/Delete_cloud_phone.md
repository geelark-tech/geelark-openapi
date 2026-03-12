API Description
-----------------

Batch Delete Cloud Phones

Request URL
-----------

* `https://openapi.geelark.com/open/v1/phone/delete`

Request Method
--------------

* POST

Request Parameters
------------------

| Parameter | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| ids | Yes | array\[string\] | List of cloud phone IDs, Limit to 100 elements | Refer to the request example |

Request Example
---------------
```json
{
    "ids":[
        "123456ABCDEF",
        "123456ABCDEF"
    ]
}
```

Response Data Description
-------------------------

| Parameter | Type | Description |
| --- | --- | --- |
| totalAmount | integer | Total number of requested IDs |
| successAmount | integer | Total number of successful IDs |
| failAmount | integer | Total number of failed IDs |
| failDetails | array\[FailDetails\] | Failure details |

### Failure Details <FailDetails>

| Parameter | Type | Description |
| --- | --- | --- |
| code | integer | Error code |
| id | integer | Cloud phone ID |
| msg | string | Error message |

Response Example
----------------

```json
{
    "code": 0,
    "msg": "success",
    "traceId": "12345ABCDEF",
    "data": {
        "totalAmount": 4,
        "successAmount": 2,
        "failAmount": 2,
        "failDetails": [
            {
                "code": 42001,
                "id": "12345ABCDEF",
                "msg": "env not found"
            },
            {
                "code": 43009,
                "id": "12345ABCDEF",
                "msg": "env is started"
            }
        ]
    }
}
```

Error Codes
-----------

Below are specific error codes for the API. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 42001 | Cloud phone does not exist |
| 43009 | Cloud phone is started, cannot delete |
| 43010 | Cloud phone is starting, cannot delete |
| 43021 | The cloud phone is in use, please try again later |