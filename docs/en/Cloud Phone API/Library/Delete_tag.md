[TOC]

## Interface Description
delete material tag


## Request URL

- `https://openapi.geelark.com/open/v1/material/tag/del`

## Request Method
- POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| ids | Yes | array[string] | tag id | Refer to Request Example  |


## Request Example
```json
{
    &quot;ids&quot; : [&quot;570461738663674391&quot;]
}
```


## Response Example

```json
{
  &quot;traceId&quot;: &quot;ACEB0CFEB887F99CB989BC9D9FF92BBC&quot;,
  &quot;code&quot;: 0,
  &quot;msg&quot;: &quot;success&quot;,
  &quot;data&quot;: {
    &quot;totalAmount&quot;: 2,
    &quot;successAmount&quot;: 1,
    &quot;failAmount&quot;: 1,
    &quot;failDetails&quot;: [
      {
        &quot;code&quot;: 43022,
        &quot;id&quot;: &quot;528953724308030464&quot;,
        &quot;msg&quot;: &quot;tag not found&quot;
      }
    ]
  }
}
```


## Response Data Description
| Parameter Name | Type              | Description          |
| ------------- | ------------------ | ------------ |
| totalAmount    | integer           | Total delete requests |
| successAmount  | integer           | Total successes      |
| failAmount     | integer           | Total failures       |
| failDetails    | array[FailDetails] | Failure details      |


### Failure Details &lt;FailDetails&gt;


| Parameter Name | Type              | Description          |
| ------------ | ---------- | ------------ |
| code           | integer | Error code  |
| id             | string  | Tag ID     |
| msg            | string  | Error msg   |



## Error Codes
Below are specific error codes for the API. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| ------ | ---------- |
| 43022  | tag not found |









