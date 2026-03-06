[TOC]

## Interface Description

Used to close the corresponding browser. You need to specify the environment ID.


## Request URL

- `http://localhost:40185/api/v1/browser/stop`

## Request method


- POST


## Request Parameters


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | browser id | 539893235657500146 |


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
    &quot;msg&quot;: &quot;success&quot;
}
```


## Error Code


Below are specific error codes for this interface. For other error codes, please refer to [Browser Error Codes](https://open.geelark.com/api/browser-error-codes).

| Error Code | Description |
| --- | --- |
| -1 | Shutdown failed |
| 43028 | The sub-user does not have permissions for this environment group |

