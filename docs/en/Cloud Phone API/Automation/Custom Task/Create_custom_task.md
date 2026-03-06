[TOC]

API Description
-----------
Get the task flows by Task flow query API first

Request URL
-----------

* `https://openapi.geelark.com/open/v1/task/rpa/add`

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
| flowId | Yes | string | Task flow id(The ID field of the Task flow query response) |
| paramMap | No | object | Task flow parameter, the file type should be an array |

Request Example
----------------

```json
{
	&quot;name&quot;:&quot;test&quot;,
	&quot;remark&quot;:&quot;test remark&quot;,
	&quot;scheduleAt&quot;: 1741846843,
	&quot;id&quot;:&quot;557536075321468390&quot;,
	&quot;flowId&quot;: &quot;562316072435344885&quot;,
	&quot;paramMap&quot;: {
		&quot;Title&quot;: &quot;video&quot;,
		&quot;Desc&quot;: &quot;this is video&quot;,
		&quot;Video&quot;: [&quot;https://material.geelark.com/a.mp4&quot;]
	}
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
