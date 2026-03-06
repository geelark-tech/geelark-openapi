
API Description
---------------

For changing plan, the API only supports upgrading plan. Downgrading plan should be completed through the GeeLark client

Request URL
-----------
- `https://openapi.geelark.com/open/v1/pay/plan/upgrade`

Request Method
--------------
- POST

Request Parameters
------------------

| Parameter | Required | Type | Description | Example |
| ----------- | -------| -----------|----------- |--------- |
| profilesId   | yes     |   string  | profiles id，it can be obtained through the 'get plan list' API | 497540679501610040 |
|parallelsNum|yes|int|the parallels number should be greater than or equal to the parallels number of the current plan| 1 |
|monthlyRentalNum|yes|int|the monthly rental number should be greater than or equal to the monthly rental number of the current plan| 1  |
|days|no|int| Parameter was required when the plan was expired, renewal duration：30/90/180/360 day| 30 |
|promoCode|no|string|promo code| PromoCode |

Request Example
---------------

```json
{
    "profilesId": "497540679501610040",
    "parallelsNum":1,
    "monthlyRentalNum" : 1
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
| 41002 | only support upgrade plan, please operate on the client side |
| 41003 | promo code is invalid |

