[TOC]

Request URL
-----------

* `https://openapi.geelark.com/open/v1/rpa/task/faceBookAutoComment`

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
| postAddress | Yes | string | Post address, up to 128 characters |
| comment | Yes | \[\]string | Comments, up to 10, each comment up to 8000 characters |
| keyword | Yes | \[\]string | Keywords, up to 10, each keyword up to 100 characters |

Request Example
----------------
```json
{
 "name":"test",
 "remark":"test remark",
 "scheduleAt": 1741846843,
 "id":"557536075321468390",
 "postAddress":"https://abc.com",
 "comment": ["test1", "test2"],
 "keyword": ["k1", "k2"]
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