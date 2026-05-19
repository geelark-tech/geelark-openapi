## API Description

API: Renew plan.

## Request URL

* `https://openapi.geelark.com/open/v1/pay/plan/continue`

## Request Method

* POST

## Authentication

All requests are `POST` with `Content-Type: application/json`.

Required headers:

- `traceId`: Version 4 UUID (uppercase recommended)
- **Token mode:** `Authorization: Bearer YOUR_API_TOKEN`
- **Key mode:** `appId`, `traceId`, `ts`, `nonce`, `sign` (see [Request Instructions](../User%20Guide/Cloud%20Phone/Request_Instructions.md))

## Request Parameters

| Parameter | Required | Type | Description | Example |
| ----------- | -------| -----------|----------- |--------- |
|days|yes|integer|renewal duration：30/90/180/360 day| 30 |
|promoCode|no|string|promo code| PromoCode |

## Request Example

```json
{
    "days":30,
    "promoCode" : "GeeLark666"
}
```

## Response Example

```json
{
    "traceId": "A3889654BA84B91CBABF8535B83AEABB",
    "code": 0,
    "msg": "success"
}
```

## Response Data Description

| Field | Type | Description |
| --- | --- | --- |
| traceId | string | Request identifier |
| code | integer | `0` = success |
| msg | string | Status message |
| data | object | Response payload (see example) |

## Error Codes

See [Cloud Phone Error Codes](../Error%20Codes/Cloud_Phone_Error_Codes.md). Interface-specific codes may also appear in the response `msg` / `code` fields.
