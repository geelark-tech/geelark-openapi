## Interface Description

- Create tags with specified **name and color (optional)**.
- Support batch creation.
- If no color is selected during creation, the default color is **white**.

### Color List

- `white`
- `red`
- `blue`
- `green`
- `yellow`
- `purple`

## Request URL

- `https://openapi.geelark.com/open/v1/tag/add`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type          | Description       | Example           |
| -------------- | -------- | ------------- | ----------------- | ----------------- |
| list           | Yes      | array[TagItem] | Tag data list     | Refer to Request Example |

### list Data List <TagItem>

| Parameter Name | Required | Type   | Description | Example                   |
| -------------- | -------- | ------ | ----------- | ------------------------- |
| name           | Yes      | string | Tag name, up to 30 characters    | tag                       |
| color          | No       | string | Tag color   | white, see color list for details |

## Request Example

```json
{
  "list": [
    {
      "name": "tagEmpty"
    },
    {
      "name": "tagRed",
      "color": "red"
    },
    {
      "name": "tagBlue",
      "color": "blue"
    },
    {
      "name": "tagGreen",
      "color": "green"
    },
    {
      "name": "tagYellow",
      "color": "yellow"
    },
    {
      "name": "tagPurple",
      "color": "purple"
    },
    {
      "name": "tagWhite",
      "color": "white"
    },
    {
      "name": "tagWhite2",
      "color": ""
    },
    {
      "name": "tagInvalid",
      "color": "abc"
    }
  ]
}
```

## Response Example

```json
{
  "traceId": "BC78266DA98F18EA9278B9C89AF9BB9B",
  "code": 0,
  "msg": "success",
  "data": {
    "totalAmount": 9,
    "successAmount": 8,
    "failAmount": 1,
    "successDetails": [
      {
        "id": "528989565877224448",
        "name": "tagWhite2",
        "color": "white"
      },
      {
        "id": "528989565877289984",
        "name": "tagBlue",
        "color": "blue"
      },
      {
        "id": "528989565877355520",
        "name": "tagGreen",
        "color": "green"
      },
      {
        "id": "528989565894001664",
        "name": "tagYellow",
        "color": "yellow"
      },
      {
        "id": "528989565894067200",
        "name": "tagPurple",
        "color": "purple"
      },
      {
        "id": "528989565894132736",
        "name": "tagWhite",
        "color": "white"
      },
      {
        "id": "528989565894198272",
        "name": "tagEmpty",
        "color": "white"
      },
      {
        "id": "528989565910778880",
        "name": "tagRed",
        "color": "red"
      }
    ],
    "failDetails": [
      {
        "code": 43023,
        "name": "tagInvalid",
        "msg": "tag color not found"
      }
    ]
  }
}
```

## Response Data Description

| Parameter Name | Type               | Description          |
| -------------- | ------------------ | -------------------- |
| totalAmount    | integer            | Total requests       |
| successAmount  | integer            | Total successes      |
| failAmount     | integer            | Total failures       |
| successDetails | array[SuccessDetails] | Success details      |
| failDetails    | array[FailDetails]   | Failure details      |

### successDetails Success Info <SuccessDetails>

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| id             | string | Tag ID      |
| name           | string | Tag name    |
| color          | string | Tag color   |

### failDetails Failure Info <FailDetails>

| Parameter Name | Type    | Description |
| -------------- | ------- | ----------- |
| code           | integer | Error code  |
| name           | string  | Tag name    |
| msg            | string  | Error msg   |

## Error Codes

Below are the specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 43020      | Tag name is empty                  |
| 43021      | Tag name already exists            |
| 43023      | Tag color not supported, see color list |
