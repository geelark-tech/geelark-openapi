## API Description

Delete proxy

## Request URL

- `https://openapi.geelark.com/open/v1/proxy/delete`

## Request Method

*   POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| ids | Yes | array[string] | Proxy ID list, up to 100 IDs. | Reference request example |

## Request Examples

```json
{
	"ids": [
		"493188072704313353"
	]
}
```

## Response Data Description

| Parameter Name | Type | Description |
| --- | --- | --- |
| totalAmount | integer | Total processed, duplicate IDs provided will not be counted. |
| successAmount | integer | Number of successfully processed items |
| failAmount | integer | Number of failed items |
| failDetails | array[FailDetail] | Failed proxy information |

### FailDetail Failed proxy information

| Parameter Name | Type | Description |
| id | string | Proxy ID |
| code | integer | Error code, refer to failure code and message |
| msg| string | Error message, refer to failure code and message |

### Failure code and message

| code | msg |
| - | - |
| 40005 | proxy not found |
| 40010 | proxy binds to the environment |

## Response Example

```json
{
    "traceId": "31ec87cd-b8a0-40c1-984e-9d6b8a483322",
    "code": 40006,
    "msg": "partial success",
    "data": {
		"totalAmount": 2,
		"successAmount": 1,
		"failAmount": 1,
		"failDetails": [
			{
				"id": "493188072704313353",
				"code": 40005,
				"msg": "proxy not found"
			}
		]
	}
}
```
## Error Codes

Please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).
