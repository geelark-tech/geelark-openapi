[TOC]

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
    &quot;traceId&quot;: &quot;BBBA5FE8B3A8FBDEB0209321B43BEB80&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: [
        {
            &quot;id&quot;: &quot;497540679501610040&quot;,
            &quot;price&quot;: 5,
            &quot;level&quot;: 0,
            &quot;envNum&quot;: 5,
            &quot;freeTime&quot;: 60,
            &quot;openEnvNumOneDay&quot;: 1000,
            &quot;createEnvNumOneDay&quot;: 25
        },
        {
            &quot;id&quot;: &quot;512719311391949750&quot;,
            &quot;price&quot;: 19,
            &quot;level&quot;: 1,
            &quot;envNum&quot;: 20,
            &quot;freeTime&quot;: 60,
            &quot;openEnvNumOneDay&quot;: 10000,
            &quot;createEnvNumOneDay&quot;: 200
        }
    ]
}
```

