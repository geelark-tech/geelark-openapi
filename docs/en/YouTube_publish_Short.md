Request URL
-----------

* `https://openapi.geelark.com/open/v1/rpa/task/youtubePubShort`

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
| title | Yes | string | Title, up to 100 characters |
| video | Yes | string | Video,  to upload videos, please refer to [Upload Temporary Files to GeeLark](https://open.geelark.com/api/upload-getUrl) |
| sameStyleUrl | No | string | Same style URL, up to 500 characters |
| sameStyleVoice | Yes | int | Same style volume, 0-100. If you do not want to send the same URL, just send 0 |
| originalVoice | Yes | int | Original voice volume, 0-100. If you do not want to send the same URL, just send 0 |

Request Example
----------------
```json
{
 "name":"test",
 "remark":"test remark",
 "scheduleAt": 1741846843,
 "id":"557536075321468390",
 "title":"title",
 "video": "https://material.geelark.com/a.mp4",
 "SameStyleUrl": "https://www.abc.com",
 "sameStyleVoice":50,
 "originalVoice":50
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