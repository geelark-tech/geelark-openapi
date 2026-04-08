Request URL
-----------

* `https://openapi.geelark.com/open/v1/rpa/task/instagramEdit`

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
| profilePicture | No | array[string] | Avatar |
| nickname | No | string | Nickname |
| username | No | string | Username |
| biography | No | string | Biography |
| linkURL | No | string | Link URL |
| linkTitle | No | string | Link Title |

Request Example
----------------
```json
{
 "name":"test",
 "remark":"test remark",
 "scheduleAt": 1741846843,
 "id":"557536075321468390",
 "nickname":"myName",
 "username": "myName"
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