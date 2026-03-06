
## Interface Description

- Retrieve group information.

## Request URL

- `https://openapi.geelark.com/open/v1/group/list`

## Request Method

- POST

## Request Parameters

### Pagination Parameters

| Parameter Name | Required | Type    | Description                                      | Example |
| -------------- | -------- | ------- | ------------------------------------------------ | ------- |
| page           | Yes      | integer | Page number, minimum is 1                        | 1       |
| pageSize       | Yes      | integer | Number of items per page, minimum is 1, maximum is 100 | 10      |

### Query Parameters

| Parameter Name | Required | Type          | Description       | Example           |
| -------------- | -------- | ------------- | ----------------- | ----------------- |
| ids            | No       | array[string] | List of group IDs | Refer to Request Example |
| names          | No       | array[string] | List of group names | Refer to Request Example |
| remarks        | No       | array[string] | List of group remarks | Refer to Request Example |

## Request Example

### Without Query Conditions

```json
{
  "page": 1,
  "pageSize": 5
}
```

### Query by IDs

```json
{
  "page": 1,
  "pageSize": 5,
  "ids": ["528995439832269824", "528985080069096448"]
}
```

### Query by Names

```json
{
  "page": 1,
  "pageSize": 5,
  "names": ["groupRemark", "testRemark"]
}
```

### Query by Remarks

```json
{
  "page": 1,
  "pageSize": 5,
  "remarks": ["remark", "test"]
}
```

## Response Example

```json
{
  "traceId": "A25B0025BA886B1EB2679AAAAC599998",
  "code": 0,
  "msg": "success",
  "data": {
    "total": 2,
    "page": 1,
    "pageSize": 5,
    "list": [
      {
        "id": "528995439832269824",
        "name": "groupRemark",
        "remark": "remark"
      },
      {
        "id": "528985080069096448",
        "name": "testRemark",
        "remark": "test"
      }
    ]
  }
}
```

## Response Data Description

| Parameter Name | Type              | Description          |
| -------------- | ----------------- | -------------------- |
| total          | integer           | Total count          |
| page           | integer           | Page number          |
| pageSize       | integer           | Page size            |
| list           | array[Group]      | Group list           |
| failDetails    | array[FailDetails] | Failure details      |

### list Group List <Group>

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| id             | string | Group ID    |
| name           | string | Group name  |
| remark         | string | Group remark|

### failDetails Failure Info <FailDetails>

| Parameter Name | Type    | Description                                      |
| -------------- | ------- | ------------------------------------------------ |
| code           | integer | Error code                                       |
| type           | integer | Failure type: 1-Group ID, 2-Group name, 3-Group remark |
| param          | string  | Failed parameter                                 |
| msg            | string  | Failure message                                  |

## Error Codes

Below are the specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 43032      | Group does not exist               |
| 43033      | Group name does not exist          |
| 43034      | Group remark does not exist        |
