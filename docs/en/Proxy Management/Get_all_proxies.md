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
	&quot;page&quot;: 1,
	&quot;pageSize&quot;: 1,
	&quot;ids&quot;: [
		&quot;493188072704313353&quot;
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
    &quot;traceId&quot;: &quot;31ec87cd-b8a0-40c1-984e-9d6b8a483322&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
		&quot;total&quot;: 1,
		&quot;page&quot;: 1,
		&quot;pageSize&quot;: 1,
		&quot;list&quot;: [
			{
				&quot;id&quot;: &quot;493188072704313353&quot;,
				&quot;serialNo&quot;: 1,
				&quot;scheme&quot;: &quot;socks5&quot;,
				&quot;server&quot;: &quot;192.3.8.1&quot;,
				&quot;port&quot;: 8000,
				&quot;username&quot;: &quot;admin&quot;,
				&quot;password&quot;: &quot;admin&quot;
			}
		]
	}
}
```
## Error Codes

Please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).
