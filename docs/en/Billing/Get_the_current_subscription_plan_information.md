## API Description

Get the current subscription plan information.

## Request URL

* `https://openapi.geelark.com/open/v1/pay/plan/info`

## Request Method

* POST

## Authentication

All requests are `POST` with `Content-Type: application/json`.

Required headers:

- `traceId`: Version 4 UUID (uppercase recommended)
- **Token mode:** `Authorization: Bearer YOUR_API_TOKEN`
- **Key mode:** `appId`, `traceId`, `ts`, `nonce`, `sign` (see [Request Instructions](../User%20Guide/Cloud%20Phone/Request_Instructions.md))

## Request Parameters

_No request body parameters._

## Request Example

_See parameter table._

## Response Example

```json
{
    "traceId": "928AD6F698AE1840ACEA9A5EA858179B",
    "code": 0,
    "msg": "success",
    "data": {
        "plan": 1,
        "profiles": 1000,
        "monthlyRental": 13,
        "parallels": 3,
        "expirationTime": 1774596449,
        "monthlyFee": 777.4,
        "availableProfiles": 160,
        "availableMonthlyRentals": 0
    }
}
```

## Response Data Description

| Parameter Name | Type | Description |
| --- | --- | --- |
| plan | integer | Subscription type: 0 = Base, 1 = Pro |
| profiles | integer | Total number of profiles |
| monthlyRental | integer | Number of monthly rental devices |
| parallels | integer | No extra charge as long as the number of cloud phone profiles opened at the same time does not exceed your parallel limit. |
| expirationTime | integer | Plan expiration timestamp |
| monthlyFee | float | Monthly billing amount |
| availableProfiles | integer | Number of available profiles |
|availableMonthlyRentals|integer| Number of available monthly rental devices  |

## Error Codes

See [Cloud Phone Error Codes](../Error%20Codes/Cloud_Phone_Error_Codes.md). Interface-specific codes may also appear in the response `msg` / `code` fields.
