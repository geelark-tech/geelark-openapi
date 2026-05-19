## API Description

API: Delete cloud phone.

## Request URL

* `https://openapi.geelark.com/open/v1/phone/delete`

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
| ids | Yes | array\[string\] | List of cloud phone IDs, Limit to 100 elements | Refer to the request example |

## Request Example

```json
{
    "ids":[
        "123456ABCDEF",
        "123456ABCDEF"
    ]
}
```

## Response Example

```json
{
    "code": 0,
    "msg": "success",
    "traceId": "12345ABCDEF",
    "data": {
        "totalAmount": 4,
        "successAmount": 2,
        "failAmount": 2,
        "failDetails": [
            {
                "code": 42001,
                "id": "12345ABCDEF",
                "msg": "env not found"
            },
            {
                "code": 43009,
                "id": "12345ABCDEF",
                "msg": "env is started"
            }
        ]
    }
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
