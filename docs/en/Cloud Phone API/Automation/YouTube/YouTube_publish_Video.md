[TOC]

Request URL
-----------

* `https://openapi.geelark.com/open/v1/rpa/task/youtubePubVideo`

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
| description | Yes | string | Description, up to 5000 characters |
| video | Yes | string | Video,  to upload videos, please refer to [Upload Temporary Files to GeeLark](https://open.geelark.com/api/upload-getUrl)  |

Request Example
----------------
```json
{
 &quot;name&quot;:&quot;test&quot;,
 &quot;remark&quot;:&quot;test remark&quot;,
 &quot;scheduleAt&quot;: 1741846843,
 &quot;id&quot;:&quot;557536075321468390&quot;,
 &quot;title&quot;:&quot;title&quot;,
 &quot;description&quot;:&quot;description&quot;,
 &quot;video&quot;: &quot;https://material.geelark.com/a.mp4&quot;
}
```

Response Example
----------------

```json
{
    &quot;traceId&quot;: &quot;A4D8BCF69B878A71AC589F5CB1D80EAB&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;taskId&quot;: &quot;558017255909123564&quot;
    }
}
```