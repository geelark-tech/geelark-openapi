[TOC]

## API Description

Get all proxies

## Request URL

- `https://openapi.geelark.com/open/v1/proxy/list`

## Request Method

*   POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| page | Yes | integer | Page number, minimum value is 1. | 1 |
| pageSize | Yes | integer | Number of items per page, minimum is 1, maximum is 100. | 1 |
| ids | No | array[string] | Proxy ID list | Reference request example |

## Request Examples

```json
{
	"page": 1,
	"pageSize": 1,
	"ids": [
		"493188072704313353"
	]
}
```

## Response Data Description

| Parameter Name | Type | Description |
| --- | --- | --- |
| total | integer | Total number of items |
| page | integer | Page number |
| pageSize | integer | Number of items per page |
| list | array[ProxyListItem] | The list of proxy information items |

### ProxyListItem 代理信息项

| Parameter Name | Type | Description |
| --- | --- | --- |
| id | string | Proxy ID |
| serialNo | int | Proxy serial number |
| scheme | string | Proxy types，socks5，http，https |
| server | string | Proxy address |
| port | integer | Proxy port |
| username | string | Proxy username |
| password | string | Proxy password |

## Response Example

```json
{
    "traceId": "31ec87cd-b8a0-40c1-984e-9d6b8a483322",
    "code": 0,
    "msg": "success",
    "data": {
		"total": 1,
		"page": 1,
		"pageSize": 1,
		"list": [
			{
				"id": "493188072704313353",
				"serialNo": 1,
				"scheme": "socks5",
				"server": "192.3.8.1",
				"port": 8000,
				"username": "admin",
				"password": "admin"
			}
		]
	}
}
```
## Error Codes

Please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).
