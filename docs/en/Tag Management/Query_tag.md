[TOC]


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
  &quot;page&quot;: 1,
  &quot;pageSize&quot;: 5
}
```

### Query by IDs

```json
{
  &quot;page&quot;: 1,
  &quot;pageSize&quot;: 5,
  &quot;ids&quot;: [&quot;528989565910778880&quot;, &quot;528989565894198272&quot;]
}
```

### Query by Names

```json
{
  &quot;page&quot;: 1,
  &quot;pageSize&quot;: 5,
  &quot;names&quot;: [&quot;tagRed&quot;, &quot;tagWhite&quot;]
}
```

### Query by Colors

```json
{
  &quot;page&quot;: 1,
  &quot;pageSize&quot;: 5,
  &quot;colors&quot;: [&quot;blue&quot;, &quot;red&quot;]
}
```

## Response Example

```json
{
  &quot;traceId&quot;: &quot;913AE8DBBBB48B70825EBAABB11B91BD&quot;,
  &quot;code&quot;: 0,
  &quot;msg&quot;: &quot;success&quot;,
  &quot;data&quot;: {
    &quot;total&quot;: 24,
    &quot;page&quot;: 1,
    &quot;pageSize&quot;: 5,
    &quot;list&quot;: [
      {
        &quot;id&quot;: &quot;528989565877355520&quot;,
        &quot;name&quot;: &quot;tagGreen&quot;,
        &quot;color&quot;: &quot;green&quot;
      },
      {
        &quot;id&quot;: &quot;528989565877289984&quot;,
        &quot;name&quot;: &quot;tagBlue&quot;,
        &quot;color&quot;: &quot;blue&quot;
      },
      {
        &quot;id&quot;: &quot;528989565894067200&quot;,
        &quot;name&quot;: &quot;tagPurple&quot;,
        &quot;color&quot;: &quot;purple&quot;
      },
      {
        &quot;id&quot;: &quot;528989565910778880&quot;,
        &quot;name&quot;: &quot;tagRed&quot;,
        &quot;color&quot;: &quot;red&quot;
      },
      {
        &quot;id&quot;: &quot;528989565894198272&quot;,
        &quot;name&quot;: &quot;tagEmpty&quot;,
        &quot;color&quot;: &quot;white&quot;
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

### list Tag List &lt;Tag&gt;

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| id             | string | Tag ID      |
| name           | string | Tag name    |
| color          | string | Tag color   |

### failDetails Failure Info &lt;FailDetail&gt;

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

