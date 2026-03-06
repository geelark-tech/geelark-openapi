[TOC]

API Description
---------------

Get the current subscription plan information.  
Rate limit: **1 request per minute**

Request URL
-----------

*   `https://openapi.geelark.com/open/v1/pay/plan/info`
    

Request Method
--------------

*   `POST`
    

Response Parameters
-------------------

| Parameter Name | Type | Description |
| --- | --- | --- |
| plan | integer | Subscription type: 0 = Base, 1 = Pro |
| profiles | integer | Total number of profiles |
| monthlyRental | integer | Number of monthly rental devices |
| parallels | integer | No extra charge as long as the number of cloud phone profiles opened at the same time does not exceed your parallel limit. |
| expirationTime | integer | Plan expiration timestamp |
| monthlyFee | float | Monthly billing amount |
| availableProfiles | integer | Number of available profiles |
|availableMonthlyRentals|integer| Number of available monthly rental devices  |

Response Example
----------------

```json
{
    &quot;traceId&quot;: &quot;928AD6F698AE1840ACEA9A5EA858179B&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;plan&quot;: 1,
        &quot;profiles&quot;: 1000,
        &quot;monthlyRental&quot;: 13,
        &quot;parallels&quot;: 3,
        &quot;expirationTime&quot;: 1774596449,
        &quot;monthlyFee&quot;: 777.4,
        &quot;availableProfiles&quot;: 160,
        &quot;availableMonthlyRentals&quot;: 0
    }
}
```


