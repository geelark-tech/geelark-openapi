[TOC]

## Interface Description
Retrieve the callback interface URL set by the user.

## Request URL

- `https://openapi.geelark.com/open/v1/callback/get`

## Request Method

- POST

## Response Example

```json
{
    &quot;traceId&quot;: &quot;9CEA6CC9B5BB68BBAE4ABDF9BE5AC89D&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;url&quot;: &quot;http://example.geelark.com/phone/callback/test&quot;
    }
}
```

## Response Body Data Description

| Parameter Name | Type | Description |
| ----------- | ----------- | ----------- |
| url | string | The set callback URL |

## Error Codes

Below are the specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 51001 | Callback URL not set |