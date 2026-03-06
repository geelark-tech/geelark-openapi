[TOC]

## API Description

- Hide the cloud phone accessibility in app.
- Currently supports Android 12, 13, 15 devices.
- It will overwrite the old configuration

## Request URL

- `https://openapi.geelark.com/open/v1/phone/hideAccessibility`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| ids | Yes | array[string] | clound phone id array | [&quot;599257164413959866&quot;] |
| pkgName | Yes | array[string] | app package name array |  [&quot;com.zhiliaoapp.musically&quot;] |

## Request Example

```json
{
	&quot;ids&quot;: [&quot;599257164413959866&quot;],
	&quot;pkgName&quot; : [&quot;com.zhiliaoapp.musically&quot;]
}
```

## Response Data Description
### failDetails 
| Parameter Name | Type | Description |
| ----------- | -----------|----------- |
| id | integer   | cloud phone id  |
| code | integer   | error code  |
| msg | string   | error msg  |

## Response Example

```json
{
	&quot;traceId&quot;: &quot;A17A45A3B3A49AB5A1BDB654B7C82B81&quot;,
	&quot;code&quot;: 0,
	&quot;msg&quot;: &quot;success&quot;,
	&quot;data&quot;: {
		&quot;failDetails&quot;: [
			{
				&quot;id&quot;: &quot;599257164413959866&quot;,
				&quot;code&quot;: 42001,
				&quot;msg&quot;: &quot;env not found&quot;
			}
		]
	}
}
```

## Error Codes

Below are specific error codes for this interface. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 42001 | cloud phone not exist |
| 43037 | does not support this devices |




