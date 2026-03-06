## API Description

You can call this interface to cancel tasks that are in the following status:

*   `Waiting for execution`
- `In progress`

## Request URL

*   `https://openapi.geelark.com/open/v1/task/cancel`

## Request Method

*   POST

## Request Parameters

| Parameter Name | Required | Type | Description |
| --- | --- | --- | --- |
| ids | Yes | array\[string\] | A task ID array, with a maximum of 100 entries. |

## Request Example

```json
{
    "ids": ["123321", "456654"]
}
```

## Response Data Description

| Parameter Name | Type | Description |
| --- | --- | --- |
| totalAmount | integer | Total number processed |
| successAmount | integer | Number of successfully processed tasks |
| failAmount | integer | Number of failed tasks |
| failDetails | array\[FailDetail\] | Details of failed tasks |

### FailDetail

| Parameter Name | Type | Description |
| --- | --- | --- |
| id | string | Task ID |
| code | integer | Error code |
| msg | string | Error message |

## Response Examples

### All Success

```json
{
    "traceId": "123456ABCEDF",
    "code": 0,
    "msg": "success",
	"data": {
		"totalAmount": 10,
		"successAmount": 10,
		"failAmount": 0
	}
}
```
### All Fail

```json
{
    "traceId": "123456ABCEDF",
    "code": 40000,
    "msg": "unknown error"
}
```
or
```json
{
    "traceId": "123456ABCEDF",
    "code": 40009,
    "msg": "process all failure",
	"data": {
		"totalAmount": 1,
		"successAmount": 0,
		"failAmount": 1,
		"failDetails": [
			"id": "123456ABCEDF"
			"code": "48001",
			"msg": "the current task status does not allow the operation"
		]
	}
}
```

### Partial Success

```json
{
    "traceId": "123456ABCEDF",
    "code": 40006,
    "msg": "partial success",
	"data": {
		"totalAmount": 2,
		"successAmount": 1,
		"failAmount": 1,
		"failDetails": [
			"id": "123456ABCEDF"
			"code": "48001",
			"msg": "the current task status does not allow the operation"
		]
	}
}
```

## Error Codes

For outer-layer response error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

## Single Task Processing Error Codes

| Error Code | Description |
| --- | --- |
| 48001 | Task status does not allow cancellation |
| 40000 | Unknown error |