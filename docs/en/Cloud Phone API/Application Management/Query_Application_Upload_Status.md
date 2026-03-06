##  API Description

Query Application Upload Status

## Request URL

- `https://openapi.geelark.com/open/v1/app/upload/status`

## Request Method

- POST

## Request Parameters

| Parameter | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| taskId | Yes | string | Task ID | 1830906144634757120 |

## Request Example

```json
{
    "taskId" :  "1830906144634757120"
}
```

## Response Data Description

| Parameter | Type | Description |
| --- | --- | --- |
| status | int | Status (0: in the process of being uploaded; 1: uploaded successfully; 2: upload failed; 3: not approved in review) |
| appName | string | Application name |
| appIcon | string | Application icon |
| appId | string | Application ID |
| versionId | string | Application version ID |

## Response Example

```json
{
    "traceId": "B9C9A787A1B559A6B883A171A7EA129B",
    "code": 0,
    "msg": "success",
    "data": {
        "status": 1,
        "appName": "パワサカ",
        "appIcon": "https://material.geelark.cn/app/icon/20240903/223wgZeZq3.jpg",
        "appId": "1813124121385549826",
        "versionId": "1813124121435881473"
    }
}
```

## Error Codes

The following are specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 42007 | Task does not exist |