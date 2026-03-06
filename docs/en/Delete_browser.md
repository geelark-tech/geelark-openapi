## Interface Description

Delete unnecessary environments. Batch deletion is supported, but the number of environments that can be deleted at one time cannot exceed 100.


## Request URL

- `http://localhost:40185/api/v1/browser/delete`

## Request method


- POST


## Request Parameters


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| envIds | Yes | array[string] | Browser ID array, up to 100 | [“539893235657500146”] |


## Request Example


```json
{
  "envIds": ["539893235657500146"]
}
```


## Example response


```json
{
	"traceId":"123456ABCDEF",
	"code":0,
	"msg":"success",
	"data":{
		"busyIds":["539893235657500146"],
		"serverErrIds":["539893235657500147"],
		"successIds":["539893235657500148"]
	}
}
```


## Response body data description


| Parameter Name | Type | Description |
| --- | --- | --- |
| successIds | array[string] | IDs of environments that were successfully deleted |
| busyIds | array[string] | IDs of environments currently in use |
| serverErrIds | array[string] | IDs of environments handling exceptions |


## Error Code


Below are specific error codes for this interface. For other error codes, please refer to [Browser Error Codes](https://open.geelark.com/api/browser-error-codes).

| Error Code | Description |
| --- | --- |
| 43028 | The sub-user does not have the permission of the environment group |


