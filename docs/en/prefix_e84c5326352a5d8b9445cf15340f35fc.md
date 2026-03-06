[TOC]

API Documentation
-----------------

* Send SMS to cloud phone. Before sending, please start the cloud phone first.

Request URL
-----------

* `https://openapi.geelark.com/open/v1/phone/sendSms`

Request Method
--------------

* POST

Request Parameters
------------------

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | Cloud phone environment ID (Currently supports only Android 12 , 13, 14, 15 devices) | 526209711930868736 |
| phoneNumber | Yes | string | Phone number | +17723504471 |
| text | Yes | string | SMS content | xxxx |

Request Example
---------------


```json
{
 "id": "526209711930868736",
 "phoneNumber": "+17723504471",
 "text": "your tk code: 6666"
}
```
----------------

```json
{
 "traceId": "9E681400B2983A5390F4B7C8BF1BF2B7",
 "code": 0,
 "msg": "success",
 "data": {}
}
```

| Error Code | Description |
| --- | --- |
| 52001 | This type of cloud phone does not support sending SMS. |