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
	"page": 1,
	"pageSize": 1
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
	 "traceId": "914969A485BE1AE584ECB4D19AF83EBA",
	 "code": 0,
	 "msg": "success",
	 "data": {
		 "total": 1,
		 "page": 1,
		 "pageSize": 1,
		 "items": [
			 {
				 "id": "562316072435344885",
				 "title": "video flow",
				 "desc": "this is a video flow",
				 "params": [
					 "Title",
					 "Desc",
					 "Video"
				 ]
			 }
		 ]
	 }
}
```