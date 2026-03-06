[TOC]

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
    &quot;taskId&quot; :  &quot;1830906144634757120&quot;
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
    &quot;traceId&quot;: &quot;B9C9A787A1B559A6B883A171A7EA129B&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;status&quot;: 1,
        &quot;appName&quot;: &quot;パワサカ&quot;,
        &quot;appIcon&quot;: &quot;https://material.geelark.cn/app/icon/20240903/223wgZeZq3.jpg&quot;,
        &quot;appId&quot;: &quot;1813124121385549826&quot;,
        &quot;versionId&quot;: &quot;1813124121435881473&quot;
    }
}
```

## Error Codes

The following are specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 42007 | Task does not exist |