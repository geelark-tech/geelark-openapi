[TOC]

## API Description

Upload Application

## Request URL

- `https://openapi.geelark.com/open/v1/app/upload`

## Request Method

- POST

## Request Parameters

| Parameter | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| fileUrl | Yes | string | Application installation file link (supports apk, xapk only) | https://material.geelark.cn/user-upload/495622401615203830/apk/uCeztwvXpswsHPH5WFht.apk |
| desc | No | string | Remarks | Application description |

## Request Example

```json
{
    "fileUrl" : "https://material.geelark.cn/user-upload/495622401615203830/apk/uCeztwvXpswsHPH5WFht.apk",
    "desc" : "app description"
}
```

## Response Data Description

| Parameter | Type | Description |
| --- | --- | --- |
| taskId | string | Task ID for querying upload status |

## Response Example

```json
{
    "traceId": "B82825D58F85FB31B755BD6CA32A30A9",
    "code": 0,
    "msg": "success",
    "data": {
        "taskId": "1830906144634757120"
    }
}
```

## Error Codes

Please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).