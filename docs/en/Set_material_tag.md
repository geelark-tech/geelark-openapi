## Interface Description
set material tag

## Request URL

- `https://openapi.geelark.com/open/v1/material/tag/set`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type          | Description           | Example           |
| --- | --- | --- | --- | --- |
| materialsId | Yes | array[string] | material id | Refer to Request Example  |
| tagsId | No | array[string] | tags id，Each tagging operation will delete all existing tags and only retain the newly set tags | Refer to Request Example  |


## Request Example
```json
{
 "materialsId" : ["570457374221926935"],
 "tagsId" : ["570461738663674391"]
}
```


## Response Example

```json
{
    "traceId": "AC3ADD84BEA1D8D2A7DDAF8B90A8D2A8",
    "code": 0,
    "msg": "success",
    "data": {
        "failDetails": [
            {
                "id": "5704573742219269351",
                "code": 60005,
                "msg": "material not found"
            },
            {
                "id": "5704617386636743911",
                "code": 43022,
                "msg": "tag not found"
            }
        ]
    }
}
```

## Response Data Description
### failDetails Failure Info <FailDetails>


| Parameter Name | Type    | Description |
| -------------- | ------- | ----------- |
| code           | integer | Error code  |
| id             | string  | Tag ID      |
| msg            | string  | Error msg   |


## Error Codes

Below are specific error codes for the API. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 43022  | tag not found |
| 60005  | material not found |









