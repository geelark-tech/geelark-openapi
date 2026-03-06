Request URL
-----------

* `https://openapi.geelark.com/open/v1/rpa/task/instagramPubReelsImages`

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
| image | Yes | \[\]string | Images, up to 10, to upload images, please refer to [Upload Temporary Files to GeeLark](https://open.geelark.com/api/upload-getUrl) |
| sameStyleUrl | No | string | Same URL |
| aiTag | No | bool | AI tag, defaults to false. |
| publishPost | No | bool | Posting a POST request defaults to false. |

Request Example
----------------
```json
{
 "name":"test",
 "remark":"test remark",
 "scheduleAt": 1741846843,
 "id":"557536075321468390",
 "description":"description",
 "image": ["https://material.geelark.com/a.jpg"]
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