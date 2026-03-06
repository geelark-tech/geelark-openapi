[TOC]

## API Description

A task can be retried up to 5 times.  
Tasks created by the client will automatically retry up to 2 times if they fail, while tasks created via the API will not automatically retry.  
If the task still fails after automatic retries, this interface can be called to retry the task.  
The interface can be called to retry the task when the task is in the following states:

*   `Task Failed`
*   `Task Canceled`

## Request URL

*   `https://openapi.geelark.com/open/v1/task/restart`

## Request Method

*   POST

## Request Parameters

| Parameter Name | Required | Type | Description |
| --- | --- | --- | --- |
| ids | Yes | array\[string\] | Array of task IDs |

## Request Example

```json
{
    &quot;ids&quot;: [&quot;123321&quot;, &quot;456654&quot;]
}
```

## Response Data Description

| Parameter Name | Type | Description |
| --- | --- | --- |
| totalAmount | integer | Total number of tasks processed |
| successAmount | integer | Number of tasks processed successfully |
| failAmount | integer | Number of tasks failed to process |
| failDetails | array\[FailDetail\] | Details of failed tasks |

### FailDetail

| Parameter Name | Type | Description |
| --- | --- | --- |
| id | string | Task ID |
| code | integer | Error code |
| msg | string | Error message |

## Response Examples

### All Successful

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

### All Failed


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

For outer response error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

### Single Task Processing Error Codes

| Error Code | Description |
| --- | --- |
| 40005 | Environment has been deleted |
| 48000 | Task retry limit reached |
| 48001 | Task status does not allow retry |
| 48002 | Task does not exist |
| 48003 | The task resource has expired |
