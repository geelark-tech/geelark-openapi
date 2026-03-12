## Interface Description

Get Browser Task Details

## Request URL

- `http://localhost:40185/api/v1/browser/task/detail`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| ----------- | -------| -----------|----------- |----------- |
| taskId | Yes | string | Task ID | 497652752864775437 |


## Request Example

```json
{
    "taskId": "497652752864775437"
}
```

## Response Body Data Description

| Parameter Name | Type | Description |
| ----------- | -----------|----------- |
|id|string|Task ID|
|eid|string|Environment ID|
|name|string|Task Name|
|remark|string|Task Remark|
|serialName|string|Environment Name|
|status|integer|Task Status, 1-Waiting for Execution 2-Executing 3-Task Completed 4-Task Failed 7-Task Cancellation |
|startAt|integer|Start time, timestamp in seconds|
|finishAt|integer|End time, timestamp in seconds|
|cost|integer|Time elapsed in seconds|
|resultCode|integer|Task result code, refer to task failure codes and reasons|
|resultDesc|string|Task result description, refer to task failure codes and reasons|
|scheduleAt|integer|Task scheduled execution time, timestamp in seconds|
|logs|array[string]|Task logs|

### Task Failure Codes and Reasons

| Failure Code | Failure Reason |
| - | - |
|20001|Task start time is earlier than current time|
|20002|Browser failed to start|
|29999|Task was interrupted|

## Response Example

```json
{
	"traceId":"2XsBK1HDR",
	"code":0,
	"msg":"success",
	"data":{
		"id":"609019758523737585",
		"eid":"600729455865921210",
		"name":"task20260303182734",
		"remark":"",
		"serialName":"",
		"status":3,
		"startAt":1772533706,
		"finishAt":1772533707,
		"cost":1,
		"resultCode":0,
		"resultDesc":"success",
		"scheduleAt":1772533659,
		"logs":["[2026-03-03 10:28:26 118] New Tab:"]
	}
}
```