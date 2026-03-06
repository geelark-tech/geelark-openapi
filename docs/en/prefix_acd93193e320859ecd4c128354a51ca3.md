[TOC]

## Interface Description

Get browser task list

## Request URL

- `http://localhost:40185/api/v1/browser/task/search`


## Request method


- POST


## Request Parameters


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| page | No | integer | Page number, defaults to 1 if not specified | 1 |
| pageSize | No | integer | Page size, maximum 100, defaults to 10 if not specified | 10 |
| taskIds | No | array[string] | Task ID | Refer to request example |


## Request Example

```json
{
    "page": 1,
	"pageSize": 10,
    "taskIds": ["497652752864775437"]
}
```

## Response Data Description

| Parameter Name | Type | Description |
| --- | --- | --- |
|total|integer|Total number of data|
|page|integer|Page number|
|pageSize|integer|Page size|
|list|array[Task]|Data list|

### Task

| Parameter Name | Type | Description |
| --- | --- | --- |
|id|string|Task ID|
|eid|string|Environment ID|
|name|string|Task Name|
|remark|string|Task Remark|
|serialName|string|Environment Name|
|status|integer|Task Status, 1-Waiting for Execution 2-Executing 3-Task Completed 4-Task Failed 7-Task Cancelled|
|startAt|integer|Start Time, Second-level Timestamp|
|finishAt|integer|End Time, Second-level Timestamp|
|cost|integer|Time Elapsed in Seconds|
|resultCode|integer|Task Result Code, Refer to Task Failure Code and Reason|
|resultDesc|string|Task Result Description, Refer to Task Failure Code and Reason|
|scheduleAt|integer|Task Scheduled Execution Time, Second-level Timestamp|

### Task Failure Codes and Reasons

| Failure Code | Failure Reason |
| - | - |
|20001|The task started earlier than the current time|
|20002|Browser failed to start|
|29999|The task was interrupted|

## Example response

```json
{
	"traceId":"2XsBK1HDR",
	"code":0,
	"msg":"success",
	"data":{
		"total":1,
		"page":1,
		"pageSize":10,
		"list":[
			{
				"id":"497652752864775437",
				"eid":"497652752864775438",
				"name":"myTask",
				"remark":"",
				"serialName":"",
				"status":3,
				"startAt":1762912197,
				"finishAt":1762912497,
				"cost":300,
				"resultCode":0,
				"resultDesc":"success",
				"scheduleAt":1762912197
			}
		]
	}
}
```


## Error Code


Please refer to [Browser Error Codes](https://open.geelark.com/api/browser-error-codes).

