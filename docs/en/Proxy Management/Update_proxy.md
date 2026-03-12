## API Description

Update proxy

## Request URL

- `https://openapi.geelark.com/open/v1/proxy/update`

## Request Method

*   POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| list | Yes | array[ProxyUpdateItem] | The list of proxy information items can contain up to 100 entries. | Reference request example |

### ProxyUpdateItem proxy information items

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | Proxy ID | 493188072704313353 |
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
			"id": "493188072704313353",
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
| totalAmount | integer | Total processed, duplicate IDs provided will not be counted. |
| successAmount | integer | Number of successfully processed items |
| failAmount | integer | Number of failed items |
| failDetails | array[FailDetail] | Failed proxy information |

### FailDetail Failed proxy information

| Parameter Name | Type | Description |
| --- | --- | --- |
| id | string | Proxy ID |
| code | integer | Error code, refer to failure code and message |
| msg| string | Error message, refer to failure code and message |

### Failure code and message

| code | msg |
| - | - |
| 40005 | proxy not found |
| 40000 | unknown error |
| 45003 | proxy not allow |
| 45004 | check proxy failed |
| 45007 | proxy already exists |
| 45008 | proxy type not allow |

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
				"id": "493188072704313353",
				"code": 40005,
				"msg": "proxy not found"
			}
		]
	}
}
```
## Error Codes

Please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).