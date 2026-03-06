## API Description

Batch shut down cloud phones.

## Request URL

*   `https://openapi.geelark.com/open/v1/phone/stop`

## Request Method

*   POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| ids | Yes | array\[string\] | List of cloud phone IDs | See request example |

## Request Example

```json
{
    "ids":[
        "123456ABCDEF",
        "123456ABCDEF",
        "123456ABCDEF",
        "123456ABCDEF"
    ]
}
```

## Response Example

```json
{
    "code": 0,
    "msg": "成功",
    "traceId": "123456ABCDEF",
    "data": {
        "totalAmount": 4,
        "successAmount": 3,
        "failAmount": 1,
        "successDetails": [
            {
                "id": "123456ABCDEF",
                "serialName": "name1",
                "status": 0
            },
            {
                "id": "123456ABCDEF",
                "serialName": "name2",
                "status": 1
            },
            {
                "id": "123456ABCDEF",
                "serialName": "name3",
                "status": 1
            }
        ],
        "failDetails": [
            {
                "code": 42001,
                "id": "123456ABCDEF",
                "msg": "env not found"
            }
        ]
    }
}
```

## Response Data Description

| Parameter Name | Type | Description |
| --- | --- | --- |
| totalAmount | integer | Total number of requested IDs |
| successAmount | integer | Number of successfully shut down IDs |
| failAmount | integer | Number of failed IDs |
| failDetails | array\[FailDetails\] | Information about failures |

### failDetails Failure Information &lt;FailDetails&gt;

| Parameter Name | Type | Description |
| --- | --- | --- |
| code | integer | Error code |
| id | integer | Cloud phone ID |
| msg | string | Error message |

## Error Codes

Below are specific error codes for this interface. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 42001 | Cloud phone does not exist |
| 43005 | Cloud phone is executing a task |
| 43006 | Cloud phone is being remotely connected |