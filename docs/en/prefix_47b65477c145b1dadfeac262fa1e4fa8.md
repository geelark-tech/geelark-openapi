[TOC]

## Interface Description
After the user requests the API, they can process relevant information in the callback interface they have set up.

## Request URL

- `https://openapi.geelark.com/open/v1/callback/set`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| url | Yes | string | Callback interface address | http://example.geelark.com/phone/callback/test |

## Request Example
```json
{
    "url": "http://example.geelark.com/phone/callback/test"
}
```

## Response Example

```json
{
    "traceId": "960B32039F84AA489514ADCC9ADA909F",
    "code": 0,
    "msg": "success"
}
```