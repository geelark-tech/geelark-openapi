[TOC]


## Interface Description

- Delete the corresponding tags.

## Request URL

- `https://openapi.geelark.com/open/v1/tag/delete`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type          | Description           | Example           |
| -------------- | -------- | ------------- | --------------------- | ----------------- |
| ids            | Yes      | array[string] | List of tag IDs to delete | Refer to Request Example |

## Request Example

```json
{
  "ids": ["528989565877224448", "528953724308030464"]
}
```

## Response Example

```json
{
  "traceId": "ACEB0CFEB887F99CB989BC9D9FF92BBC",
  "code": 0,
  "msg": "success",
  "data": {
    "totalAmount": 2,
    "successAmount": 1,
    "failAmount": 1,
    "failDetails": [
      {
        "code": 43022,
        "id": "528953724308030464",
        "msg": "tag not found"
      }
    ]
  }
}
```

## Response Data Description

| Parameter Name | Type              | Description          |
| -------------- | ----------------- | -------------------- |
| totalAmount    | integer           | Total delete requests |
| successAmount  | integer           | Total successes      |
| failAmount     | integer           | Total failures       |
| failDetails    | array[FailDetails] | Failure details      |

### failDetails Failure Info <FailDetails>

| Parameter Name | Type    | Description |
| -------------- | ------- | ----------- |
| code           | integer | Error code  |
| id             | string  | Tag ID      |
| msg            | string  | Error msg   |

## Error Codes

Below are the specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 43022      | Tag does not exist                 |
