
## Interface Description

- Retrieve tag information.

**Refer to the Create Tag API for the list of tag colors.**

## Request URL

- `https://openapi.geelark.com/open/v1/tag/list`

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
| ids            | No       | array[string] | List of tag IDs   | Refer to Request Example |
| names          | No       | array[string] | List of tag names | Refer to Request Example |
| colors         | No       | array[string] | List of tag colors| Refer to Request Example |

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
  "ids": ["528989565910778880", "528989565894198272"]
}
```

### Query by Names

```json
{
  "page": 1,
  "pageSize": 5,
  "names": ["tagRed", "tagWhite"]
}
```

### Query by Colors

```json
{
  "page": 1,
  "pageSize": 5,
  "colors": ["blue", "red"]
}
```

## Response Example

```json
{
  "traceId": "913AE8DBBBB48B70825EBAABB11B91BD",
  "code": 0,
  "msg": "success",
  "data": {
    "total": 24,
    "page": 1,
    "pageSize": 5,
    "list": [
      {
        "id": "528989565877355520",
        "name": "tagGreen",
        "color": "green"
      },
      {
        "id": "528989565877289984",
        "name": "tagBlue",
        "color": "blue"
      },
      {
        "id": "528989565894067200",
        "name": "tagPurple",
        "color": "purple"
      },
      {
        "id": "528989565910778880",
        "name": "tagRed",
        "color": "red"
      },
      {
        "id": "528989565894198272",
        "name": "tagEmpty",
        "color": "white"
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
| list           | array[Tag]        | Tag list             |
| failDetails    | array[FailDetail] | Failure details      |

### list Tag List <Tag>

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| id             | string | Tag ID      |
| name           | string | Tag name    |
| color          | string | Tag color   |

### failDetails Failure Info <FailDetail>

| Parameter Name | Type    | Description                                      |
| -------------- | ------- | ------------------------------------------------ |
| code           | integer | Error code                                       |
| type           | integer | Failure type: 1-Tag ID, 2-Tag name, 3-Tag color  |
| param          | string  | Failed parameter                                 |
| msg            | string  | Failure message                                  |

## Error Codes

Below are the specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 43022      | Tag does not exist                 |
| 43023      | Tag color does not exist           |
| 43024      | Tag name does not exist            |

