[TOC]

## API Description

Delete proxy

## Request URL

- `https://openapi.geelark.com/open/v1/proxy/delete`

## Request Method

*   POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| ids | Yes | array[string] | Proxy ID list, up to 100 IDs. | Reference request example |

## Request Examples

```json
{
	&quot;ids&quot;: [
		&quot;493188072704313353&quot;
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
| id | string | Proxy ID |
| code | integer | Error code, refer to failure code and message |
| msg| string | Error message, refer to failure code and message |

### Failure code and message

| code | msg |
| - | - |
| 40005 | proxy not found |
| 40010 | proxy binds to the environment |

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
				&quot;id&quot;: &quot;493188072704313353&quot;,
				&quot;code&quot;: 40005,
				&quot;msg&quot;: &quot;proxy not found&quot;
			}
		]
	}
}
```
## Error Codes

Please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).
