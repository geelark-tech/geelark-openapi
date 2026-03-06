[TOC]


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
  &quot;page&quot;: 1,
  &quot;pageSize&quot;: 5
}
```

### Query by IDs

```json
{
  &quot;page&quot;: 1,
  &quot;pageSize&quot;: 5,
  &quot;ids&quot;: [&quot;528995439832269824&quot;, &quot;528985080069096448&quot;]
}
```

### Query by Names

```json
{
  &quot;page&quot;: 1,
  &quot;pageSize&quot;: 5,
  &quot;names&quot;: [&quot;groupRemark&quot;, &quot;testRemark&quot;]
}
```

### Query by Remarks

```json
{
  &quot;page&quot;: 1,
  &quot;pageSize&quot;: 5,
  &quot;remarks&quot;: [&quot;remark&quot;, &quot;test&quot;]
}
```

## Response Example

```json
{
  &quot;traceId&quot;: &quot;A25B0025BA886B1EB2679AAAAC599998&quot;,
  &quot;code&quot;: 0,
  &quot;msg&quot;: &quot;success&quot;,
  &quot;data&quot;: {
    &quot;total&quot;: 2,
    &quot;page&quot;: 1,
    &quot;pageSize&quot;: 5,
    &quot;list&quot;: [
      {
        &quot;id&quot;: &quot;528995439832269824&quot;,
        &quot;name&quot;: &quot;groupRemark&quot;,
        &quot;remark&quot;: &quot;remark&quot;
      },
      {
        &quot;id&quot;: &quot;528985080069096448&quot;,
        &quot;name&quot;: &quot;testRemark&quot;,
        &quot;remark&quot;: &quot;test&quot;
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

### list Group List &lt;Group&gt;

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| id             | string | Group ID    |
| name           | string | Group name  |
| remark         | string | Group remark|

### failDetails Failure Info &lt;FailDetails&gt;

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
