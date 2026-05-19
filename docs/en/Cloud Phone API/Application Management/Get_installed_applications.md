## API Description

API: Get installed applications.

## Request URL

* `https://openapi.geelark.com/open/v1/app/list`

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
| envId | Yes | string | Cloud phone environment ID | 123456654321 |
| page | Yes | integer | Page number, minimum is 1 | 1 |
| pageSize | Yes | integer | Number of items per page, minimum is 1, maximum is 100 | 10 |

## Request Example

```json
{
    "envId" : "1809135651036667904",
    "page" : 1,
    "pageSize" : 5
}
```

## Response Example

```json
{
    "traceId": "123",
    "code": 0,
    "msg": "success",
    "data": {
        "items": [
            {
                "appIcon": "http://cmp1-prod.zxpcloud.com/apps/io.tm.k.drama/K-DRAMA_1716451323126.png",
                "appId": "1793552962123993090",
                "appName": "K-DRAMA",
                "appVersionId": "1793552962140770305",
                "installStatus": 1,
                "installTime": "2024-07-10 23:07:56",
                "packageName": "io.tm.k.drama",
                "versionCode": "21120300",
                "versionName": "1.0.1"
            }
        ],
        "total": 1,
        "page": 1,
        "pageSize": 5
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
