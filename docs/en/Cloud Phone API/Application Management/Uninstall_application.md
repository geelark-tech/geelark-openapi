[TOC]

## API Description

Uninstall an app.

## Request URL

* `https://openapi.geelark.com/open/v1/app/uninstall`

## Request Method

* POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| envId | Yes | string | Cloud phone environment ID | 1809135651036667904 |
| packageName | Yes | string | Application package name| com.zhiliaoapp.musically |
~~| appVersionId | No | string |App version ID (either appVersionId or packageName must be provided) | 1793552962140770305 |~~

## Request Example

```json
{
 &quot;envId&quot; : &quot;1809135651036667904&quot;,
 &quot;packageName&quot; : &quot;com.zhiliaoapp.musically&quot;
}
```

## Response Example

```json
{
 &quot;traceId&quot;: &quot;123&quot;,
 &quot;code&quot;: 0,
 &quot;msg&quot;: &quot;success&quot;
}
```

## Error Codes

The following are specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 42001 | The specified cloud phone does not exist |
| 42002 | The cloud phone is not in a running state |
| 42005 | The corresponding app is not installed |