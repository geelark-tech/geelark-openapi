## API Description

Query and return the cookies of a specified environment. Only one environment can be queried at a time.


## Request URL

- `http://localhost:40185/api/v1/browser/getCookie`

## Request Method


- POST






## Request Parameters


| Parameter | Required | Type | Example | Description
| --- | --- | --- | --- | --- |
| id | Yes | string | "123456789" | Browser ID |


## Request Example


```json
{
    "id": "123456789"
}
```


## Response Example


```json
{
"traceId": "123456ABCDEF",
    "code": 0,
    "msg": "success",
    "data": {
        "cookies": "[]"
    }
}
```