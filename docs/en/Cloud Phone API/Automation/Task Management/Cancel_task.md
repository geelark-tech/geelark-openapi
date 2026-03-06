[TOC]

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
    &quot;ids&quot;: [&quot;123321&quot;, &quot;456654&quot;]
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
    &quot;traceId&quot;: &quot;123456ABCEDF&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
	&quot;data&quot;: {
		&quot;totalAmount&quot;: 10,
		&quot;successAmount&quot;: 10,
		&quot;failAmount&quot;: 0
	}
}
```
### All Fail

```json
{
    &quot;traceId&quot;: &quot;123456ABCEDF&quot;,
    &quot;code&quot;: 40000,
    &quot;msg&quot;: &quot;unknown error&quot;
}
```
or
```json
{
    &quot;traceId&quot;: &quot;123456ABCEDF&quot;,
    &quot;code&quot;: 40009,
    &quot;msg&quot;: &quot;process all failure&quot;,
	&quot;data&quot;: {
		&quot;totalAmount&quot;: 1,
		&quot;successAmount&quot;: 0,
		&quot;failAmount&quot;: 1,
		&quot;failDetails&quot;: [
			&quot;id&quot;: &quot;123456ABCEDF&quot;
			&quot;code&quot;: &quot;48001&quot;,
			&quot;msg&quot;: &quot;the current task status does not allow the operation&quot;
		]
	}
}
```

### Partial Success

```json
{
    &quot;traceId&quot;: &quot;123456ABCEDF&quot;,
    &quot;code&quot;: 40006,
    &quot;msg&quot;: &quot;partial success&quot;,
	&quot;data&quot;: {
		&quot;totalAmount&quot;: 2,
		&quot;successAmount&quot;: 1,
		&quot;failAmount&quot;: 1,
		&quot;failDetails&quot;: [
			&quot;id&quot;: &quot;123456ABCEDF&quot;
			&quot;code&quot;: &quot;48001&quot;,
			&quot;msg&quot;: &quot;the current task status does not allow the operation&quot;
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