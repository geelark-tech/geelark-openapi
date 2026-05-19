## API Description

API: Send SMS to cloud phone.

## Request URL

* `https://openapi.geelark.com/open/v1/phone/sendSms`

## Request Method

* POST

## Authentication

All requests are `POST` with `Content-Type: application/json`.

Required headers:

- `traceId`: Version 4 UUID (uppercase recommended)
- **Token mode:** `Authorization: Bearer YOUR_API_TOKEN`
- **Key mode:** `appId`, `traceId`, `ts`, `nonce`, `sign` (see [Request Instructions](../../User%20Guide/Cloud%20Phone/Request_Instructions.md))

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | Cloud phone environment ID (Currently supports only Android 12 , 13, 14, 15 devices) | 526209711930868736 |
| phoneNumber | Yes | string | Phone number | +17723504471 |
| text | Yes | string | SMS content | xxxx |

## Request Example

```json
{
 "id": "526209711930868736",
 "phoneNumber": "+17723504471",
 "text": "your tk code: 6666"
}
```
----------------

```json
{
 "traceId": "9E681400B2983A5390F4B7C8BF1BF2B7",
 "code": 0,
 "msg": "success",
 "data": {}
}
```

| Error Code | Description |
| --- | --- |
| 52001 | This type of cloud phone does not support sending SMS. |

## Response Example

_Standard envelope; see Response Data Description._

## Response Data Description

| Field | Type | Description |
| --- | --- | --- |
| traceId | string | Request identifier |
| code | integer | `0` = success |
| msg | string | Status message |
| data | object | Response payload (see example) |

## Error Codes

See [Cloud Phone Error Codes](../../Error%20Codes/Cloud_Phone_Error_Codes.md). Interface-specific codes may also appear in the response `msg` / `code` fields.
