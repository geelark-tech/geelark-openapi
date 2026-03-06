[TOC]

Request URL
-----------

*   `https://openapi.geelark.com/open/v1/analytics/accounts/delete`
    

Request Method
--------------

*   POST
    

Request Parameters
------------------

| Parameter | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| channel | Yes | int | Platform | 0: TikTok, 1: YouTube, 2: Instagram |
| account | Yes | string | Account name, maximum length 64 characters | See request example |

Request Example
---------------

```json
{
    &quot;channel&quot;:0,
    &quot;account&quot;:&quot;xxxx&quot;
}
```

Response Example
----------------

```json
{
	&quot;traceId&quot;: &quot;9D1A84D6A2A8F9A8A5CD9BA7B7E84281&quot;,
	&quot;code&quot;: 0,
	&quot;msg&quot;: &quot;success&quot;
}
```