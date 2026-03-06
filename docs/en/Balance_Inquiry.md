API Description
---------------

Query account balance, this API has a rate limit of 10 requests per minute.

Request URL
-----------

*   `https://openapi.geelark.com/open/v1/pay/wallet`
    

Request Method
--------------

*   POST
    

Response Body Description
-------------------------

| Parameter | Type | Description |
| --- | --- | --- |
| balance | float | Balance |
| giftMoney | float | Gifted amount |
| availableTimeAddOn | int   | Remaining time add-on |

Response Example
----------------


```json
{
	 "traceId": "9C798E6CA2AB58348E2C974EA8E8AB8B",
	"code": 0,
	 "msg": "success",
	 "data": {
		"balance": 1549.77,
		"giftMoney": 0,
		"availableTimeAddOn" : 10
	}
}
```
