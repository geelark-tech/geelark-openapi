[TOC]

Request URL
-----------

*   `https://openapi.geelark.com/open/v1/analytics/accounts/add`
    

Request Method
--------------

*   POST
    

Request Parameters
------------------

| Parameter | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| channel | Yes | int | Platform | 0: TikTok, 1: YouTube, 2: Instagram |
| accountsData | Yes | array\[accountsData\] | Account information. The array supports up to 200 elements | See request example |

### accountsData

| Parameter | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| account | Yes | string | Account name, maximum length 64 characters | See request example |
| remark | No | string | Remark information | See request example |

Request Example
---------------

```json
{
    &quot;channel&quot;:0,
    &quot;accountsData&quot;: [
        {
            &quot;account&quot;:&quot;XXX&quot;,
            &quot;remark&quot;:&quot;remark xxx&quot;
        }
    ]
}
```
Response Parameters
-------------------

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| bizCode | Yes | int | Business status code: 0 = all successful; 1 = the current number of accounts exceeds the limit; 2 = partially successful, with failed items exceeding the limit |
| successCount | Yes | int | Number of successfully added accounts |
| failCount | Yes | int | Number of failed additions |
| repeatCount | Yes | int | Number of duplicate additions |

Response Example
----------------

```json
{
	&quot;traceId&quot;: &quot;9D1A84D6A2A8F9A8A5CD9BA7B7E84281&quot;,
	&quot;code&quot;: 0,
	&quot;msg&quot;: &quot;success&quot;,
	&quot;data&quot;: {
    	&quot;bizCode&quot;: 0,
    	&quot;successCount&quot;: 1,
    	&quot;failCount&quot;: 0,
    	&quot;repeatCount&quot;: 0
	}
}
```
