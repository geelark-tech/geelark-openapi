Request URL
-----------

* `https://openapi.geelark.com/open/v1/rpa/task/tiktokEdit`

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
| avatar | No | string | Avatar URL, refer to the User Guide - File Upload for creating automation tasks; the uploaded image should have a 1:1 aspect ratio, otherwise the edit will fail |
| nickName | No | string | Nickname, up to 50 characters |
| bio | No | string | Bio, up to 200 characters |
| site | No | string | Website, up to 100 characters, please provide a URL starting with http/https |

Request Example
----------------
```json
{
 "name":"test",
 "remark":"test remark",
 "scheduleAt": 1741846843,
 "id":"557536075321468390",
 "avatar":"https://singapore-upgrade.geelark.com/a.jpg",
 "nickName": "test",
 "bio":"test",
 "site":"https://www.abc.com" 
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