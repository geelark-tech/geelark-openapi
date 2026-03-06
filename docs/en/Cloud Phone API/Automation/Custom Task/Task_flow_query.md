[TOC]

Request URL
-----------

* `https://openapi.geelark.com/open/v1/task/flow/list`

Request Method
--------------

* POST

Request Parameters
------------------

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| page | Yes | integer | Page number, minimum value is 1. |
| pageSize | Yes | integer | Number of items per page, minimum is 1, maximum is 100. |

Request Example
----------------

```json
{
	&quot;page&quot;: 1,
	&quot;pageSize&quot;: 1
}
```

## Response Data Description

| Field Name | Type | Description |
| ----------- | -----------|----------- |
| total | integer | Total number of items |
| page | integer | Page number |
| pageSize | integer | Number of items per page |
| items | array[TaskFlow] | Task flow array  |

### TaskFlow

| Field Name | Type | Description |
| ----------- | -----------|----------- |
| id | string   | Task flow id |
| title | string   | Task flow title |
| desc | string   | Task flow description |
| params | array[string]   | Task flow parameter field name |

Response Example
----------------

```json
{
	 &quot;traceId&quot;: &quot;914969A485BE1AE584ECB4D19AF83EBA&quot;,
	 &quot;code&quot;: 0,
	 &quot;msg&quot;: &quot;success&quot;,
	 &quot;data&quot;: {
		 &quot;total&quot;: 1,
		 &quot;page&quot;: 1,
		 &quot;pageSize&quot;: 1,
		 &quot;items&quot;: [
			 {
				 &quot;id&quot;: &quot;562316072435344885&quot;,
				 &quot;title&quot;: &quot;video flow&quot;,
				 &quot;desc&quot;: &quot;this is a video flow&quot;,
				 &quot;params&quot;: [
					 &quot;Title&quot;,
					 &quot;Desc&quot;,
					 &quot;Video&quot;
				 ]
			 }
		 ]
	 }
}
```