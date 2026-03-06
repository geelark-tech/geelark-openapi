[TOC]

## Interface Description

- Modify group information including name and remark.

## Request URL

- `https://openapi.geelark.com/open/v1/group/update`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type       | Description           | Example           |
| -------------- | -------- | ---------- | --------------------- | ----------------- |
| list           | Yes      | array[Group] | Group data            | Refer to Request Example |

### list Group Data &lt;Group&gt;

| Parameter Name | Required | Type   | Description | Example           |
| -------------- | -------- | ------ | ----------- | ----------------- |
| id             | Yes      | string | Group ID    | Refer to Request Example |
| name           | No       | string | New group name, up to 50 characters| Refer to Request Example |
| remark         | No       | string | New group remark, up to 500 characters| Refer to Request Example |

- If `name` is provided, it cannot be an empty string.

## Request Example

```json
{
  &quot;list&quot;: [
    {
      &quot;id&quot;: &quot;528995439832269824&quot;,
      &quot;name&quot;: &quot;newGroupRemark&quot;,
      &quot;remark&quot;: &quot;update remark&quot;
    }
  ]
}
```

## Response Example

```json
{
  &quot;traceId&quot;: &quot;B068F85E849B683291AE8ECCBB7B3DB9&quot;,
  &quot;code&quot;: 0,
  &quot;msg&quot;: &quot;success&quot;,
  &quot;data&quot;: {
    &quot;totalAmount&quot;: 1,
    &quot;successAmount&quot;: 1,
    &quot;failAmount&quot;: 0
  }
}
```

## Error Codes

Below are the specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 43030      | Group name is empty                |
| 43032      | Group does not exist               |
| 43035      | Operation not allowed on ungrouped |
