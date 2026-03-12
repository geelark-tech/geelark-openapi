## Interface Description

Get browser custom task flow list

## Request URL

- `http://localhost:40185/api/v1/browser/task/flow`

## Request method



- POST



## Request Parameters



| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| page | No | integer | Page number, defaults to 1 if not specified | 1 |
| pageSize | No | integer | Page size, maximum 100, defaults to 10 if not specified | 10 |



## Request Example

```json
{
    "page": 1,
	"pageSize": 10
}
```

## Response Data Description


| Parameter Name | Type | Description |
| --- | --- | --- |
|total|integer|Total number of data points|
|page|integer|Page number|
|pageSize|integer|Page size|
|list|array[Flow]|List of data points|

### Flow

| Parameter Name | Type | Description |
| --- | --- | --- |
|id|string|Task Flow ID|
|title|string|Task Flow Title|
|desc|string|Task Flow Remarks|
|params|array[string]|Task Flow Parameter Field Names|

## Example response

```json
{
	"traceId":"2XsBK1HDR",
	"code":0,
	"msg":"success",
	"data":{
		"total":1,
		"page":1,
		"pageSize":10,
		"list":[
			{
				"id":"497652752864775437",
				"title": "video flow",
				"desc": "this is a video flow",
				"params": ["Title","Desc"]
			}
		]
	}
}
```

## Error Code



Please refer to [Browser Error Codes](https://open.geelark.com/api/browser-error-codes).