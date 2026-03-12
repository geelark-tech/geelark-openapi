API Description
---------------

renew plan

Request URL
-----------
- `https://openapi.geelark.com/open/v1/pay/plan/continue`

Request Method
--------------
- POST

Request Parameters
------------------

| Parameter | Required | Type | Description | Example |
| ----------- | -------| -----------|----------- |--------- |
|days|yes|int|renewal duration：30/90/180/360 day| 30 |
|promoCode|no|string|promo code| PromoCode |

Request Example
---------------

```json
{
    "days":30,
    "promoCode" : "GeeLark666"
}
```

Response Example
----------------

```json
{
    "traceId": "A3889654BA84B91CBABF8535B83AEABB",
    "code": 0,
    "msg": "success"
}
```

Error Codes
-----------

Please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes)

| Error Code | Description |
| --- | --- |
| 41001 | balance not enough |
| 41003 | promo code is invalid |