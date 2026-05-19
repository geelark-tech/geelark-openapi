## API Description

API: Move Group.

## Request URL

* `https://openapi.geelark.com/open/v1/phone/moveGroup`

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
| envIds | Yes | array\[string\] | Array of cloud phone IDs, supports up to 100 elements | See request example |
| groupId | Yes | string | Group ID. Pass `"0"` to move to the ungrouped category | See request example |

## Request Example

```json
{
    "envIds": [
        "601876382020062634"
    ],
    "groupId": "590711571886417453"
}
```

## Response Example

```json
{
    "traceId": "B3DAFF64A7BD493CB1169D94A22BFC8D",
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
