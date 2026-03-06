## API Description

Retrieve the status of cloud phones.

## Request URL

*   `https://openapi.geelark.com/open/v1/phone/status`

## Request Method

*   POST

## Request Parameters

### Query Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| ids | Yes | array\[string\] | List of cloud phone IDs, Limit to 100 elements | See request example |

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

## Response Data Description

| Parameter Name | Type | Description |
| --- | --- | --- |
| totalAmount | integer | Total number of requested IDs |
| successAmount | integer | Total number of successful responses |
| failAmount | integer | Total number of failed responses |
| successDetails | array\[SuccessDetails\] | Information about successful responses |
| failDetails | array\[FailDetails\] | Information about failed responses |

### successDetails Success Information &lt;SuccessDetails&gt;

| Parameter Name | Type | Description |
| --- | --- | --- |
| id | string | ID of the successful cloud phone |
| serialName | string | Name of the successful cloud phone |
| status | integer | Cloud phone status code&lt;br/&gt; 0 - Started&lt;br/&gt; 1 - Starting&lt;br/&gt; 2 - Shut down&lt;br/&gt; 3 - Expired |

### failDetails Failure Information &lt;FailDetails&gt;

| Parameter Name | Type | Description |
| --- | --- | --- |
| code | int | Failure code 42001: Cloud phone does not exist |
| id | string | ID of the failed cloud phone |
| msg | string | Failure message |

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

## Error Codes

Below are specific error codes for this interface. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 42001 | Cloud phone does not exist |