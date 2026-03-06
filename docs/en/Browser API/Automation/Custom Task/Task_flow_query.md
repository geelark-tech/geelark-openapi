[TOC]


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
    &quot;page&quot;: 1,
	&quot;pageSize&quot;: 10
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
	&quot;traceId&quot;:&quot;2XsBK1HDR&quot;,
	&quot;code&quot;:0,
	&quot;msg&quot;:&quot;success&quot;,
	&quot;data&quot;:{
		&quot;total&quot;:1,
		&quot;page&quot;:1,
		&quot;pageSize&quot;:10,
		&quot;list&quot;:[
			{
				&quot;id&quot;:&quot;497652752864775437&quot;,
				&quot;title&quot;: &quot;video flow&quot;,
				&quot;desc&quot;: &quot;this is a video flow&quot;,
				&quot;params&quot;: [&quot;Title&quot;,&quot;Desc&quot;]
			}
		]
	}
}
```

## Error Code



Please refer to [Browser Error Codes](https://open.geelark.com/api/browser-error-codes).

