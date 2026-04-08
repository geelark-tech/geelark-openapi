## Request URL

- `http://localhost:40185/api/v1/browser/task/tiktokLike`

## Request method


- POST


## Request Parameters


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
|eid|Yes|string|Environment ID|497652752864775437|
|name|No|string|Task name, maximum 128 characters|myTask|
|remark|No|string|Remark, maximum 200 characters|myRemark|
|scheduleAt|Yes|integer|Schedule time, second-level timestamp|1741846843|
|videoLink|Yes|string|Video link|https://www.tiktok.com/video/38210380122|
|comment|No|string|Comment|hello|


## Request Example

```json
{
    "name":"test",
    "remark":"test remark",
    "scheduleAt": 1741846843,
    "eid":"557536075321468390",
	"videoLink": "https://www.tiktok.com/video/38210380122",
	"comment": "hello"
}
```

## Example response

```json
{
    "traceId": "A4D8BCF69B878A71AC589F5CB1D80EAB",
    "code": 0,
    "msg": "success",
    "data": {
        "taskId": "558017255909123564"
    }
}
```