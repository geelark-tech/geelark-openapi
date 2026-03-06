## API Description

Duplicate proxies will not be added.

## Request URL

- `https://openapi.geelark.com/open/v1/proxy/add`

## Request Method

*   POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| list | Yes | array[ProxyAddItem] | The list of proxy information items can contain up to 100 entries. | Reference request example |

### ProxyAddItem proxy information items

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| scheme | Yes | string | Proxy types，socks5，http，https | socks5 |
| server | Yes | string | Proxy address | 192.3.8.1 |
| port | Yes | integer | Proxy port | 8000 |
| username | No | string | Proxy username | admin |
| password | No | string | Proxy password | admin |

## Request Examples

```json
{
	"list": [
		{
			"scheme": "socks5",
			"server": "192.3.8.1",
			"port": 8000,
			"username": "admin",
			"password": "admin"
		}
	]
}
```

## Response Data Description

| Parameter Name | Type | Description |
| --- | --- | --- |
| totalAmount | integer | Total processed, the same as the number of proxy information items provided. |
| successAmount | integer | Number of successful additions |
| failAmount | integer | Number of failed additions |
| failDetails | array[FailDetail] | Failed proxy information |
| successDetails | array[SuccessDetail] | Successful proxy information |

### FailDetail Failed proxy information

| Parameter Name | Type | Description |
| --- | --- | --- |
| index | integer | Index of the provided proxy information items |
| code | integer | Error code, refer to failure code and message |
| msg| string | Error message, refer to failure code and message |

### SuccessDetail Successful proxy information

| Parameter Name | Type | Description |
| --- | --- | --- |
| index | integer | Index of the provided proxy information items |
| id | string | Proxy ID; if the provided proxy information items are the same, the proxy ID will be the same. |

### Failure code and message

| code | msg |
| - | - |
| 40000 | unknown error |
| 45003 | proxy not allow |
| 45004 | check proxy failed |
| 45007 | proxy already exists |

## Response Example

```json
{
    "traceId": "31ec87cd-b8a0-40c1-984e-9d6b8a483322",
    "code": 40006,
    "msg": "partial success",
    "data": {
		"totalAmount": 2,
		"successAmount": 1,
		"failAmount": 1,
		"failDetails": [
			{
				"index": 0,
				"code": 45007,
				"msg": "proxy already exists"
			}
		],
		"successDetails": [
			{
				"index": 1,
				"id": "493188072704313353"
			}
		]
	}
}
```
## Error Codes

Please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).
