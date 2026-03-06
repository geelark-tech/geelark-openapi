[TOC]

## Interface Description

- Delete the corresponding groups.

## Request URL

- `https://openapi.geelark.com/open/v1/group/delete`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type          | Description           | Example           |
| -------------- | -------- | ------------- | --------------------- | ----------------- |
| ids            | Yes      | array[string] | List of group IDs to delete | Refer to Request Example |

## Request Example

```json
{
  &quot;ids&quot;: [&quot;528994851237200896&quot;, &quot;528994851237135360&quot;, &quot;528984285433037824&quot;]
}
```

## Response Example

```json
{
  &quot;traceId&quot;: &quot;AA69C5B4938EDB00920099719D58C8A9&quot;,
  &quot;code&quot;: 0,
  &quot;msg&quot;: &quot;success&quot;,
  &quot;data&quot;: {
    &quot;totalAmount&quot;: 3,
    &quot;successAmount&quot;: 2,
    &quot;failAmount&quot;: 1,
    &quot;failDetails&quot;: [
      {
        &quot;code&quot;: 43032,
        &quot;id&quot;: &quot;528984285433037824&quot;,
        &quot;msg&quot;: &quot;group not found&quot;
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

### failDetails Failure Info &lt;FailDetails&gt;

| Parameter Name | Type    | Description |
| -------------- | ------- | ----------- |
| code           | integer | Error code  |
| id             | string  | Group ID    |
| msg            | string  | Error msg   |

## Error Codes

Below are the specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 43032      | Group does not exist               |
| 43035      | Operation not allowed on ungrouped |