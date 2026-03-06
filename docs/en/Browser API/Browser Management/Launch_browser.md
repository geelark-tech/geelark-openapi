[TOC]

## Interface Description

Used to start the browser, you need to specify the environment ID.

## Request URL

- `http://localhost:40185/api/v1/browser/start`

## Request method


- POST


## Request Parameters


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | browser id| 539893235657500146 |


## Request Example


```json
{
 &quot;id&quot;: &quot;539893235657500146&quot;
}
```


## Example response


```json
{
  &quot;traceId&quot;: &quot;123456ABCDEF&quot;,
  &quot;code&quot;: 0,
  &quot;msg&quot;: &quot;success&quot;,
  &quot;data&quot;:{
  	&quot;debugPort&quot;: 11000
  }
}
```





## Error Code


Below are specific error codes for this interface. For other error codes, please refer to [Browser Error Codes](https://open.geelark.com/api/browser-error-codes).


| Error Code | Description |
| --- | --- |
| -1 | Startup failed |
| 43007 | The environment is already in use |
| 43008 | The maximum number of open environments has been reached |
| 46003 | The environment is not included in the plan |
| 43028 | The sub-user does not have permissions for the environment group |
| 90002 | This environment does not exist. |
| 90003 | Insufficient disk space |
