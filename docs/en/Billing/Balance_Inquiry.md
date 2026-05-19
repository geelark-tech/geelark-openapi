## API Description

Query account balance, this API has a rate limit of 10 requests per minute.

## Request URL

* `https://openapi.geelark.com/open/v1/pay/wallet`

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
	 "traceId": "9C798E6CA2AB58348E2C974EA8E8AB8B",
	"code": 0,
	 "msg": "success",
	 "data": {
		"balance": 1549.77,
		"giftMoney": 0,
		"availableTimeAddOn" : 10
	}
}
```

## Response Data Description

| Parameter | Type | Description |
| --- | --- | --- |
| balance | float | Balance |
| giftMoney | float | Gifted amount |
| availableTimeAddOn | integer   | Remaining time add-on |

## Error Codes

See [Cloud Phone Error Codes](../Error%20Codes/Cloud_Phone_Error_Codes.md). Interface-specific codes may also appear in the response `msg` / `code` fields.
