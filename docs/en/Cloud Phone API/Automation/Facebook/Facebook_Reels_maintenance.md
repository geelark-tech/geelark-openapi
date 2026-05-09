Request URL
-----------

- `https://openapi.geelark.com/open/v1/rpa/task/facebookReelsActive`


Request Method
--------------

* POST

Request Parameters
------------------

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| name | No | string | Task name, up to 128 characters |
| remark | No | string | Remarks, up to 200 characters |
| scheduleAt | Yes | integer | Scheduled time (timestamp) |
| id | Yes | string | Cloud phone ID |
| videoNumber | Yes | integer | Estimated number of videos viewed |
| searchKeywords | No | array[string] | Search keywords |

Request Example
----------------

```json
{
  "name":"test",
  "remark":"test remark",
  "scheduleAt": 1741846843,
  "id":"557536075321468390",
  "videoNumber":10,
  "searchKeywords": ["hello"]
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