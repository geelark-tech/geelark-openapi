## API Description

Enable or disable team application auto-start

## Request URL


- `https://openapi.geelark.com/open/v1/app/setAutoStart`


## Request Method


- POST


## Request Parameters


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | Team application ID | 497652752864775437 |
| opera | Yes | integer | Operation, 0 off, 1 on | 1 |


## Request Example


```json
{
 "id": "497652752864775437",
 "opera": 1
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