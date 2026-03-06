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
    "page":1,
    "pageSize":10,
    "channel":1
}
```

Response Data Description
-------------------------

| Parameter Name | Type | Description |
| --- | --- | --- |
| total | integer | Total count |
| page | integer | Current page |
| items | array\[item\] | Account data |

Response Data Description <item>
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
    "traceId": "99793C8DABAC5970A91693E38BBA0596",
    "code": 0,
    "msg": "success",
    "data": {
        "items": [
            {
                "id": "565523829426802069",
                "account": "xxx",
                "channel": 1,
                "remark": "remark",
                "operator": "xxx",
                "created_time": 1746608069,
                "updated_time": 1746608069
            }
        ],
        "total": 1,
        "page": 1
    }
}
```