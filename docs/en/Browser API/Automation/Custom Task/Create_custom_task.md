## Interface Description

First, call the custom process query interface to obtain the browser's custom task process, and then create the task using the process ID.

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
    "name":"test",
    "remark":"test remark",
    "scheduleAt": 1741846843,
    "eid":"557536075321468390",
    "flowId": "562316072435344885",
    "paramMap": {
        "Title": "video",
        "Desc": "this is video",
        "Video": ["https://material.geelark.cn/a.mp4"]
    }
}
```


## Example response

```json
{
    "traceId": "A4D8BCF69B878A71AC589F5CB1D80EAB",
    "code": 0,
    "msg": "success",
    "data": {
        "taskId": "558017255909123564"
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