Request URL
-----------

* `https://openapi.geelark.com/open/v1/rpa/task/instagramPubReels`

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
| description | Yes | string | Caption, up to 2200 characters |
| video | Yes | \[\]string | Videos, up to 10, to upload videos, please refer to [Upload Temporary Files to GeeLark](https://open.geelark.com/api/upload-getUrl)|
| sameStyleUrl | No | string | Same URL |
| sameStyleVoice | No | int | Same volume, range 0-100 |
| originalVoice | No | int | Original volume, range 0-100 |
| aiTag | No | bool | AI tag, defaults to false. |

Request Example
----------------
```json
{
 "name":"test",
 "remark":"test remark",
 "scheduleAt": 1741846843,
 "id":"557536075321468390",
 "description":"description",
 "video": ["https://material.geelark.com/a.mp4"]
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