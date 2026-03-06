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
    &quot;fileUrl&quot; : &quot;https://material.geelark.cn/user-upload/495622401615203830/apk/uCeztwvXpswsHPH5WFht.apk&quot;,
    &quot;desc&quot; : &quot;app description&quot;
}
```

## Response Data Description

| Parameter | Type | Description |
| --- | --- | --- |
| taskId | string | Task ID for querying upload status |

## Response Example

```json
{
    &quot;traceId&quot;: &quot;B82825D58F85FB31B755BD6CA32A30A9&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;taskId&quot;: &quot;1830906144634757120&quot;
    }
}
```

## Error Codes

Please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).