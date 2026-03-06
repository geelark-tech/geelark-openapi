## API Description

Close an app.

## Request URL

*   `https://openapi.geelark.com/open/v1/app/stop`

## Request Method

*   POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| envId | Yes | string | Cloud phone environment ID | 1809135651036667904 |
| appVersionId | No | string |App version ID (either appVersionId or packageName must be provided) | 1793552962140770305 |  
| packageName | No | string | Application package name (either appVersionId or packageName must be provided)| com.zhiliaoapp.musically |

## Request Example

```json
{
    "envId" : "1809135651036667904",
    "appVersionId" : "1793552962140770305"
}
```

## Response Example

```json
{
    "traceId": "123",
    "code": 0,
    "msg": "success"
}
```

## Error Codes

The following are specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 42001 | The specified cloud phone does not exist |
| 42002 | The cloud phone is not in a running state |
| 42005 | The corresponding app is not installed |