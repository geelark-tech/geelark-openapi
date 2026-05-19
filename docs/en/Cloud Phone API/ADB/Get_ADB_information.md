## API Description

API: Get ADB information.

## Request URL

* `https://openapi.geelark.com/open/v1/adb/getData`

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
| ids | Yes | array\[string\] | Array of cloud phone IDs, maximum 200 | \["526209711930868736"\] |

## Request Example

```json
{
 "ids" : ["526806961778328576","524798337208026112","524783756767134720"]
}
```

## Response Example

```json
{
    "traceId": "8AB9D6B482B679ECB5578314903B80B9",
    "code": 0,
    "msg": "success",
    "data": {
        "items": [
            {
                "code": 0,
                "id": "524783756767134720",
                "ip": "124.71.210.176",
                "pwd": "8c1da4",
                "port": "25219"
            },
            {
                "code": 42002,
                "id": "524798337208026112",
                "ip": "",
                "pwd": "",
                "port": ""
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
