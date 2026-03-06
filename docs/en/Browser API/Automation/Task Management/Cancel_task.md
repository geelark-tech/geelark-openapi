
## Interface Description

Cancel the browser task; you can cancel it while it&#039;s running or waiting to be executed.

## Request URL

- `http://localhost:40185/api/v1/browser/task/cancel`

## Request method



- POST



## Request Parameters



| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| taskId | Yes | string| task id |497652752864775437 |



## Request Example

```json
{
    "taskId": "497652752864775437"
}
```


## Example response

```json
{
	"traceId":"2XsBK1HDR",
	"code":0,
	"msg":"success"
}
```

## Error Code



Below are specific error codes for this interface. For other error codes, please refer to [Browser Error Codes](https://open.geelark.com/api/browser-error-codes).


| Error Code | Description |
| --- | --- |
|48001|Task status does not allow operation|
|48005|Only the creator is allowed to operate|
