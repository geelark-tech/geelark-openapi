API Description
---------------

Buy Time add-on, please ensure that your balance is sufficient, otherwise the purchase may fail.

Request URL
-----------
- `https://openapi.geelark.com/open/v1/pay/timeAddOn/buy`

Request Method
--------------
- POST

Request Parameters
------------------

| Parameter | Required | Type | Description | Example |
| ----------- | -------| -----------|----------- |--------- |
|minutes|yes|integer|minutes to buy | 2000 |
|promoCode|no|string|Promo Code| PromoCode |

minutes options：
2000 / 5000 / 10000 / 20000 / 50000 / 100000 / 200000 / 500000 / 1000000 / 2000000 / 5000000 / 10000000 

Request Example
---------------

```json
{
	"minutes": 2000,
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