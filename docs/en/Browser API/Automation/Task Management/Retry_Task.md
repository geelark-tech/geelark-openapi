[TOC]


## Interface Description

Retry the browser task; you can retry if the task fails or is canceled.

## Request URL

- `http://localhost:40185/api/v1/browser/task/restart`

## Request method



- POST



## Request Parameters



| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| taskId | Yes | string| task id |497652752864775437 |


## Request Example

```json
{
    &quot;taskId&quot;: &quot;497652752864775437&quot;
}
```


## Example response

```json
{
	&quot;traceId&quot;:&quot;2XsBK1HDR&quot;,
	&quot;code&quot;:0,
	&quot;msg&quot;:&quot;success&quot;
}
```

## Error Code



Below are specific error codes for this interface. For other error codes, please refer to [Browser Error Codes](https://open.geelark.com/api/browser-error-codes).


| Error Code | Description |
| --- | --- |
|48001|Task status does not allow operation|
|48005|Only the creator is allowed to operate|
