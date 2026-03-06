[TOC]


## Interface Description

- Create groups with specified **name and remark (optional)**.
- Support batch creation.

## Request URL

- `https://openapi.geelark.com/open/v1/group/add`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type             | Description           | Example           |
| -------------- | -------- | ---------------- | --------------------- | ----------------- |
| list           | Yes      | array[GroupItem] | Group data list       | Refer to Request Example |

### list Data List &lt;GroupItem&gt;

| Parameter Name | Required | Type   | Description | Example |
| -------------- | -------- | ------ | ----------- | ------- |
| name           | Yes      | string | Group name, up to 50 characters  | tag     |
| remark         | No       | string | Group remark, up to 500 characters| remark  |

## Request Example

```json
{
  &quot;list&quot;: [
    {
      &quot;name&quot;: &quot;group&quot;
    },
    {
      &quot;name&quot;: &quot;groupRemark&quot;,
      &quot;remark&quot;: &quot;remark&quot;
    },
    {
      &quot;name&quot;: &quot;groupInvalid&quot;
    }
  ]
}
```

## Response Example

```json
{
  &quot;traceId&quot;: &quot;AA6849499B949BDCBD7FA792AB1981A5&quot;,
  &quot;code&quot;: 0,
  &quot;msg&quot;: &quot;success&quot;,
  &quot;data&quot;: {
    &quot;totalAmount&quot;: 3,
    &quot;successAmount&quot;: 2,
    &quot;failAmount&quot;: 1,
    &quot;successDetails&quot;: [
      {
        &quot;id&quot;: &quot;528994851237135360&quot;,
        &quot;name&quot;: &quot;group&quot;
      },
      {
        &quot;id&quot;: &quot;528994851237200896&quot;,
        &quot;name&quot;: &quot;groupRemark&quot;,
        &quot;remark&quot;: &quot;remark&quot;
      }
    ],
    &quot;failDetails&quot;: [
      {
        &quot;code&quot;: 43031,
        &quot;name&quot;: &quot;groupInvalid&quot;,
        &quot;msg&quot;: &quot;group existed&quot;
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

### successDetails Success Info &lt;SuccessDetails&gt;

| Parameter Name | Type   | Description          |
| -------------- | ------ | -------------------- |
| id             | string | Group ID             |
| name           | string | Group name           |
| remark         | string | Remark (not shown if empty) |

### failDetails Failure Info &lt;FailDetails&gt;

| Parameter Name | Type    | Description |
| -------------- | ------- | ----------- |
| code           | integer | Error code  |
| name           | string  | Group name  |
| msg            | string  | Error msg   |

## Error Codes

Below are the specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 43030      | Group name is empty                |
| 43031      | Group name already exists          |

