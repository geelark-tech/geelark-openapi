\[TOC\]

API Description
---------------

Move Group

Request URL
-----------

*   `https://openapi.geelark.com/open/v1/phone/moveGroup`
    

Request Method
--------------

*   POST
    

Request Parameters
------------------

| Parameter | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| envIds | Yes | array\[string\] | Array of cloud phone IDs, supports up to 100 elements | See request example |
| groupId | Yes | string | Group ID. Pass `"0"` to move to the ungrouped category | See request example |

Request Example
---------------
```json
{
    "envIds": [
        "601876382020062634"
    ],
    "groupId": "590711571886417453"
}
```
Response Example
----------------
```json
{
    "traceId": "B3DAFF64A7BD493CB1169D94A22BFC8D",
    "code": 0,
    "msg": "success"
}
```