## API Description

API: Delete Account.

## Request URL

* `https://openapi.geelark.com/open/v1/analytics/accounts/delete`

## Request Method

* POST

## Authentication

All requests are `POST` with `Content-Type: application/json`.

Required headers:

- `traceId`: Version 4 UUID (uppercase recommended)
- **Token mode:** `Authorization: Bearer YOUR_API_TOKEN`
- **Key mode:** `appId`, `traceId`, `ts`, `nonce`, `sign` (see [Request Instructions](../../User%20Guide/Cloud%20Phone/Request_Instructions.md))

## Request Parameters

| Parameter | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| channel | Yes | integer | Platform | 0: TikTok, 1: YouTube, 2: Instagram |
| account | Yes | string | Account name, maximum length 64 characters | See request example |

## Request Example

```json
{
    "channel":0,
    "account":"xxxx"
}
```

## Response Example

```json
{
	"traceId": "9D1A84D6A2A8F9A8A5CD9BA7B7E84281",
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

See [Cloud Phone Error Codes](../../Error%20Codes/Cloud_Phone_Error_Codes.md). Interface-specific codes may also appear in the response `msg` / `code` fields.
