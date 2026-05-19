## API Description

Create an automation task: Task flow query. Returns `taskId` in `data`.

## Request URL

* `https://openapi.geelark.com/open/v1/task/flow/list`

## Request Method

* POST

## Authentication

All requests are `POST` with `Content-Type: application/json`.

Required headers:

- `traceId`: Version 4 UUID (uppercase recommended)
- **Token mode:** `Authorization: Bearer YOUR_API_TOKEN`
- **Key mode:** `appId`, `traceId`, `ts`, `nonce`, `sign` (see [Request Instructions](../../../User%20Guide/Cloud%20Phone/Request_Instructions.md))

## Request Parameters

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| page | Yes | integer | Page number, minimum value is 1. |
| pageSize | Yes | integer | Number of items per page, minimum is 1, maximum is 100. |

## Request Example

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

## Response Example

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

## Response Data Description

| Field | Type | Description |
| --- | --- | --- |
| traceId | string | Request identifier |
| code | integer | `0` = success |
| msg | string | Status message |
| data | object | Response payload (see example) |

## Error Codes

See [Cloud Phone Error Codes](../../../Error%20Codes/Cloud_Phone_Error_Codes.md). Interface-specific codes may also appear in the response `msg` / `code` fields.
