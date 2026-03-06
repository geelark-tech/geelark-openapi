[TOC]

Request URL
-----------

*   `https://openapi.geelark.com/open/v1/analytics/accounts/list`
    

Request Method
--------------

*   POST
    

Request Parameters
------------------

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| page | Yes | integer | Page number | 1 |
| pageSize | Yes | integer | Number of items per page (1–100) | 10 |
| account | No | string | Account name | tk\_acc |
| channel | No | int | Platform, if not provided all platforms are included | 0: TikTok 1: YouTube 2: Instagram |
| userAccount | No | string | Operator account | abc@gmail.com |

Request Example
---------------
```json
{
    &quot;page&quot;:1,
    &quot;pageSize&quot;:10,
    &quot;channel&quot;:1
}
```

Response Data Description
-------------------------

| Parameter Name | Type | Description |
| --- | --- | --- |
| total | integer | Total count |
| page | integer | Current page |
| items | array\[item\] | Account data |

Response Data Description &lt;item&gt;
--------------------------------

| Parameter Name | Type | Description |
| --- | --- | --- |
| id | string | Account ID |
| account | string | Account |
| channel | int | Platform: 0: TikTok 1: YouTube 2: Instagram |
| remark | string | Remark |
| operator | string | Username of the last operator |
| created\_time | int | Creation time |
| updated\_time | int | Last update time |

Response Example
----------------

```json
{
    &quot;traceId&quot;: &quot;99793C8DABAC5970A91693E38BBA0596&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;items&quot;: [
            {
                &quot;id&quot;: &quot;565523829426802069&quot;,
                &quot;account&quot;: &quot;xxx&quot;,
                &quot;channel&quot;: 1,
                &quot;remark&quot;: &quot;remark&quot;,
                &quot;operator&quot;: &quot;xxx&quot;,
                &quot;created_time&quot;: 1746608069,
                &quot;updated_time&quot;: 1746608069
            }
        ],
        &quot;total&quot;: 1,
        &quot;page&quot;: 1
    }
}
```