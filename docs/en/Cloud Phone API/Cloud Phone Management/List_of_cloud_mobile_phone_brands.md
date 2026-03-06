## API Description

- Get a list of cloud phone brands

## Request URL

- `https://openapi.geelark.com/open/v1/phone/brand/list`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| androidVer | Yes | integer | android version, 10-15 | 10 |

## Request Example

```json
{
	"androidVer" : 10
}
```


## Response Example

```json
{
	"traceId": "B0BA8FF29AB60B8ABF4E9A26BF08F7B9",
	"code": 0,
	"msg": "success",
	"data": [
		{
			"surfaceBrandName": "samsung",
			"surfaceModelName": "Galaxy S20+"
		}
	]
}
```

## Response Data Description

| Parameter Name | Type | Description |
| ----------- | -----------|----------- |
| surfaceBrandName | string | mobile phone brand|
| surfaceModelName | string | mobile phone model|

Error Codes
-----------

For error codes, please refer to  [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes)
