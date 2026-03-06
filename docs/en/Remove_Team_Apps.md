## API Description

Remove the application from the team applications.

## Request URL


- `https://openapi.geelark.com/open/v1/app/remove`


## Request Method


- POST


## Request Parameters


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | Team application ID | 497652752864775437 |


## Request Example


```json
{
 "id": "497652752864775437"
}
```


## Response Example


```json
{
 "traceId": "886A92FCBE9B7A52A7F583FCBD2BF6A8",
 "code": 0,
 "msg": "success"
}
```

## Error Codes


Please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

