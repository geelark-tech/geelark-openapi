Request URL
-----------

*   `https://openapi.geelark.com/open/v1/phone/importContactsResult`
    

Request Method
--------------

*   POST
    

Request Parameters
------------------

| Parameter | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| taskId | Yes | string | Task ID | See request example |

Request Example
---------------

```json
{
    "taskId": "528715748189668352"
}
```
Response Example
----------------

```json
{
    "traceId": "A62BBBF3A294487F9B49B9FFA0F84CA8",
    "code": 0,
    "msg": "success",
	"data": {
        "status": 2
    }
}
```

Response Body Data Description
------------------------------

| Parameter | Type | Description |
| --- | --- | --- |
| status | int | Task status: 1 = In progress, 2 = Successful, 3 = Failed |