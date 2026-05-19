## API Description

Get all plan info

## Request URL

* `https://openapi.geelark.com/open/v1/pay/profiles/list`

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
    "traceId": "BBBA5FE8B3A8FBDEB0209321B43BEB80",
    "code": 0,
    "msg": "success",
    "data": [
        {
            "id": "497540679501610040",
            "price": 5,
            "level": 0,
            "envNum": 5,
            "freeTime": 60,
            "openEnvNumOneDay": 1000,
            "createEnvNumOneDay": 25
        },
        {
            "id": "512719311391949750",
            "price": 19,
            "level": 1,
            "envNum": 20,
            "freeTime": 60,
            "openEnvNumOneDay": 10000,
            "createEnvNumOneDay": 200
        }
    ]
}
```

## Response Data Description

| Parameter | Type | Description |
| ----------- | -----------|----------- |
| id | string   | profiles id |
| price  |  float   | price for one month of the profiles |
| level | integer   |profiles level 0Base 1Pro |
| envNum | integer   |profiles max environment number |
| freeTime | integer   |profiles free use minute |
| openEnvNumOneDay | integer   | environment open max number in one day |
| createEnvNumOneDay | integer   | create new environment  max number in one day |

## Error Codes

See [Cloud Phone Error Codes](../Error%20Codes/Cloud_Phone_Error_Codes.md). Interface-specific codes may also appear in the response `msg` / `code` fields.
