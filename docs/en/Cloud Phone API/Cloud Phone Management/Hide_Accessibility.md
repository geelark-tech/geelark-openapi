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
| ids | Yes | array[string] | clound phone id array | ["599257164413959866"] |
| pkgName | Yes | array[string] | app package name array |  ["com.zhiliaoapp.musically"] |

## Request Example

```json
{
	"ids": ["599257164413959866"],
	"pkgName" : ["com.zhiliaoapp.musically"]
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
	"traceId": "A17A45A3B3A49AB5A1BDB654B7C82B81",
	"code": 0,
	"msg": "success",
	"data": {
		"failDetails": [
			{
				"id": "599257164413959866",
				"code": 42001,
				"msg": "env not found"
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




