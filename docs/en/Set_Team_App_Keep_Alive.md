[TOC]

## API Description

Enable or disable team app keep-alive. Only supports the Pro tier.
Only Android 12/13/14/15 are supported. One app can be kept alive at max.
On Android 12/13/15, if the app is already running when keep-alive is enabled, please restart the phone for the setting to take effect.
On Android 14, you must enable or disable keep-alive while the phone is powered on, then restart the phone for the changes to take effect.

## Request URL


- `https://openapi.geelark.com/open/v1/app/setKeepAlive`


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


Below are specific error codes for this interface. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 44001 | Please upgrade to the Pro plan |

