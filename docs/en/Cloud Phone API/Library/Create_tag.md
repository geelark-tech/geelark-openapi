[TOC]

## Interface Description
create material tag


## Request URL

- `https://openapi.geelark.com/open/v1/material/tag/create`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type          | Description           | Example           |
| --- | --- | --- | --- | --- |
| name | Yes | string | tag name（Up to 30 characters） | Refer to Request Example  |
| color | No | int |  tag color: 0 White 1 Red 2 Blue 3 Green 4 Yellow 5 Purple | Refer to Request Example|

## Request Example
```json
{
    &quot;name&quot; : &quot;test&quot;,
    &quot;color&quot; : 1
}
```


## Response Example

```json
{
    &quot;traceId&quot;: &quot;95D85F2085A6C847B2D68ABAAD591997&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;id&quot;: &quot;570461738663674391&quot;
    }
}
```

## Response Data Description

| Parameter Name | Type              | Description          |
| ----------- | -----------|----------- 
| id | string | tag id |

## Error Codes

Below are specific error codes for the API. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 60002 | tag name repeat |







