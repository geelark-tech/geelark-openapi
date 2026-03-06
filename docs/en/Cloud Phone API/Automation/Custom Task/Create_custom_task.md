API Description
-----------
Get the task flows by Task flow query API first

Request URL
-----------

* `https://openapi.geelark.com/open/v1/task/rpa/add`

Request Method
--------------

* POST

Request Parameters
------------------

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| name | No | string | Task name, up to 128 characters |
| remark | No | string | Remarks, up to 200 characters |
| scheduleAt | Yes | int | Scheduled time (timestamp) |
| id | Yes | string | Cloud phone ID |
| flowId | Yes | string | Task flow id(The ID field of the Task flow query response) |
| paramMap | No | object | Task flow parameter, the file type should be an array |

Request Example
----------------

```json
{
	"name":"test",
	"remark":"test remark",
	"scheduleAt": 1741846843,
	"id":"557536075321468390",
	"flowId": "562316072435344885",
	"paramMap": {
		"Title": "video",
		"Desc": "this is video",
		"Video": ["https://material.geelark.com/a.mp4"]
	}
}
```

Response Example
----------------

```json
{
    "traceId": "A4D8BCF69B878A71AC589F5CB1D80EAB",
    "code": 0,
    "msg": "success",
    "data": {
        "taskId": "558017255909123564"
    }
}
```
