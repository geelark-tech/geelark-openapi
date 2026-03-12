API Description
---------------

Get all plan info

Request URL
-----------

- `https://openapi.geelark.com/open/v1/pay/profiles/list`

Request Method
--------------

- POST

Response Body Description
-------------------------

| Parameter | Type | Description |
| ----------- | -----------|----------- |
| id | string   | profiles id |
| price  |  float   | price for one month of the profiles |
| level | int   |profiles level 0Base 1Pro |
| envNum | int   |profiles max environment number |
| freeTime | int   |profiles free use minute |
| openEnvNumOneDay | int   | environment open max number in one day |
| createEnvNumOneDay | int   | create new environment  max number in one day |


Response Example
----------------

```json
{
    "traceId": "BBBA5FE8B3A8FBDEB0209321B43BEB80",
    "code": 0,
    "msg": "success",
    "data": [
        {
            "id": "497540679501610040",
            "price": 5,
            "level": 0,
            "envNum": 5,
            "freeTime": 60,
            "openEnvNumOneDay": 1000,
            "createEnvNumOneDay": 25
        },
        {
            "id": "512719311391949750",
            "price": 19,
            "level": 1,
            "envNum": 20,
            "freeTime": 60,
            "openEnvNumOneDay": 10000,
            "createEnvNumOneDay": 200
        }
    ]
}
```