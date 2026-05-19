## API Description

API: Proxy Detection.

## Request URL

* `https://openapi.geelark.com/open/v1/proxy/check`

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
| --- | --- | --- | --- | --- |
| proxyQueryChannel | Yes | string | IP lookup source, supports only `IP-API` or `IP2Location` | IP2Location |
| proxyType | Yes | string | Proxy type, supports only `socks5`, `http`, or `https` | socks5 |
| server | Yes | string | Host | 185.162.130.86 |
| port | Yes | integer | Port number | 11000 |
| username | No | string | Proxy username | username |
| password | No | string | Proxy password | pass |

## Request Example

```json
{
	"proxyQueryChannel": "IP2Location",
	"proxyType": "socks5",
	"server": "185.162.130.86",
	"port": 10000,
	"username": "username",
	"password": "pass"
}
```

## Response Example

```json
{
	"traceId": "B379AA1BBBB529758ED091C480AA4285",
	"code": 0,
	"msg": "success",
	"data": {
		"detectStatus": true,
		"message": "",
		"outboundIP": "223.135.25.196",
		"countryCode": "JP",
		"countryName": "Japan",
		"subdivision": "Tokyo",
		"city": "Tokyo",
		"timezone": "Asia/Tokyo",
		"isp": "Sony Network Communications Inc."
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

See [Cloud Phone Error Codes](../Error%20Codes/Cloud_Phone_Error_Codes.md). Interface-specific codes may also appear in the response `msg` / `code` fields.
