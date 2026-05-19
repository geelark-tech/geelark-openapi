## API Description

API: Change plan.

## Request URL

* `https://openapi.geelark.com/open/v1/pay/plan/upgrade`

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
| profilesId   | yes     |   string  | profiles id，it can be obtained through the 'get plan list' API | 497540679501610040 |
|parallelsNum|yes|integer|the parallels number should be greater than or equal to the parallels number of the current plan| 1 |
|monthlyRentalNum|yes|integer|the monthly rental number should be greater than or equal to the monthly rental number of the current plan| 1  |
|days|no|integer| Parameter was required when the plan was expired, renewal duration：30/90/180/360 day| 30 |
|promoCode|no|string|promo code| PromoCode |

## Request Example

```json
{
    "profilesId": "497540679501610040",
    "parallelsNum":1,
    "monthlyRentalNum" : 1
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
