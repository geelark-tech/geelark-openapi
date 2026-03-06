[TOC]

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
	&quot;list&quot;: [
		{
			&quot;scheme&quot;: &quot;socks5&quot;,
			&quot;server&quot;: &quot;192.3.8.1&quot;,
			&quot;port&quot;: 8000,
			&quot;username&quot;: &quot;admin&quot;,
			&quot;password&quot;: &quot;admin&quot;
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
    &quot;traceId&quot;: &quot;31ec87cd-b8a0-40c1-984e-9d6b8a483322&quot;,
    &quot;code&quot;: 40006,
    &quot;msg&quot;: &quot;partial success&quot;,
    &quot;data&quot;: {
		&quot;totalAmount&quot;: 2,
		&quot;successAmount&quot;: 1,
		&quot;failAmount&quot;: 1,
		&quot;failDetails&quot;: [
			{
				&quot;index&quot;: 0,
				&quot;code&quot;: 45007,
				&quot;msg&quot;: &quot;proxy already exists&quot;
			}
		],
		&quot;successDetails&quot;: [
			{
				&quot;index&quot;: 1,
				&quot;id&quot;: &quot;493188072704313353&quot;
			}
		]
	}
}
```
## Error Codes

Please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).
