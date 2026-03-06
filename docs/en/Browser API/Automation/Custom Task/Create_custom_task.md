[TOC]


## Interface Description

First, call the custom process query interface to obtain the browser&#039;s custom task process, and then create the task using the process ID.

## Request URL

- `http://localhost:40185/api/v1/browser/task/add`

## Request method



- POST



## Request Parameters



| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
|eid|Yes|string|Environment ID|497652752864775437|
|name|No|string|Task name, maximum 128 characters|myTask|
|remark|No|string|Remark, maximum 200 characters|myRemark|
|scheduleAt|Yes|integer|Schedule time, second-level timestamp|1741846843|
|flowId|Yes|string|Task flow ID, the ID field returned by the task flow query interface|497652752864775437|
|paramMap|No|object|Task flow parameters, file types must be arrays|Refer to request example|


## Request Example

```json
{
    &quot;name&quot;:&quot;test&quot;,
    &quot;remark&quot;:&quot;test remark&quot;,
    &quot;scheduleAt&quot;: 1741846843,
    &quot;eid&quot;:&quot;557536075321468390&quot;,
    &quot;flowId&quot;: &quot;562316072435344885&quot;,
    &quot;paramMap&quot;: {
        &quot;Title&quot;: &quot;video&quot;,
        &quot;Desc&quot;: &quot;this is video&quot;,
        &quot;Video&quot;: [&quot;https://material.geelark.cn/a.mp4&quot;]
    }
}
```


## Example response

```json
{
    &quot;traceId&quot;: &quot;A4D8BCF69B878A71AC589F5CB1D80EAB&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;taskId&quot;: &quot;558017255909123564&quot;
    }
}
```

## Error Code



Below are specific error codes for this interface. For other error codes, please refer to [Browser Error Codes](https://open.geelark.com/api/browser-error-codes).


| Error Code | Description |
| --- | --- |
|43028|User does not have permission for this environment group|
|43027|Environment not supported|
|46002|Package expired, member unavailable|
|46003|Package expired, environment unavailable|
