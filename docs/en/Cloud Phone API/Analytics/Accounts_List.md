## API Description

API: Accounts List.

## Request URL

* `https://openapi.geelark.com/open/v1/analytics/accounts/list`

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
| page | Yes | integer | Page number | 1 |
| pageSize | Yes | integer | Number of items per page (1–100) | 10 |
| account | No | string | Account name | tk\_acc |
| channel | No | integer | Platform, if not provided all platforms are included | 0: TikTok 1: YouTube 2: Instagram |
| userAccount | No | string | Operator account | abc@gmail.com |

## Request Example

```json
{
    "page":1,
    "pageSize":10,
    "channel":1
}
```

## Response Example

```json
{
    "traceId": "99793C8DABAC5970A91693E38BBA0596",
    "code": 0,
    "msg": "success",
    "data": {
        "items": [
            {
                "id": "565523829426802069",
                "account": "xxx",
                "channel": 1,
                "remark": "remark",
                "operator": "xxx",
                "created_time": 1746608069,
                "updated_time": 1746608069
            }
        ],
        "total": 1,
        "page": 1
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
