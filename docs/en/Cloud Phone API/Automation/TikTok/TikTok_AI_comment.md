[TOC]

Request URL
-----------

* `https://openapi.geelark.com/open/v1/rpa/task/tiktokRandomComment`

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
| useAi | Yes | int | Whether to use AI: 1 for AI (only available for Pro users); 2 for not using AI, provide your own comment |
| comment | Yes | string | Comment content, up to 500 characters; required when useAi is 2 |
| links | No | array[string] | Specified link |

Request Example
----------------
```json
{
 &quot;name&quot;:&quot;test&quot;,
 &quot;remark&quot;:&quot;test remark&quot;,
 &quot;scheduleAt&quot;: 1741846843,
 &quot;id&quot;:&quot;557536075321468390&quot;,
 &quot;useAi&quot;:2,
 &quot;comment&quot;: &quot;test&quot;
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