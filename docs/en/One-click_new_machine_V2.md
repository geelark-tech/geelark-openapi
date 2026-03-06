[TOC]

API Description
-----------------

One-click new machine v2 interface, directly return the execution result.

Request URL
-----------

* `https://openapi.geelark.com/open/v2/phone/newOne`

Request Method
--------------

* POST

Request Parameters
------------------

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | Cloud Phone ID | See request example |
| changeBrandModel | No | bool | Whether to randomize the brand and model. true: randomize, false: keep unchanged; if not provided, it remains randomize. | true |
| keepNetType | No | bool | Preserve network connection type, defaults to false, random network connection type | true |
| keepPhoneNumber | No | bool | Preserve phone number, defaults to false, random phone number | true |
| keepRegion | No | bool | Preserve region, defaults to false, follow proxy | true |
| keepLanguage | No | bool | Preserve language, defaults to false, use English | true |

Request Example
---------------

```json
{
    "id": "528715748189668352"
}
```

Response Example
----------------

```json
{
 "traceId": "A62BBBF3A294487F9B49B9FFA0F84CA8",
 "code": 0,
 "msg": "success"
}
```
## Error Codes


Below are specific error codes for this interface. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).


| Error Code | Description |
| --- | --- |
| 42001 | cloud phone not exist |
| 44004 | maximum daily cloud phone creation limit reached |
| 43005 | cloud phone is executing task |
| 43006 | cloud phone is occupied by remote |
| 43015 | this cloud phone is not support One-click new machine |
| 45004 | proxy detect fail |
| 43038 | the equipment brand and model have been deleted. |
