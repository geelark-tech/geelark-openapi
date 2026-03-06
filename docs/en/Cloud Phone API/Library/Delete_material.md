[TOC]

## Interface Description
delete material

## Request URL

- `https://openapi.geelark.com/open/v1/material/del`

## Request Method


- POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| ids | Yes | array[string] | material id |Refer to Request Example   |

## Request Example
```json
{
    &quot;ids&quot; : [&quot;569569510948864567&quot;]
}
```


## Response Example

```json
{
    &quot;traceId&quot;: &quot;A1A84FBC88912B5A9F77B681B2A9A983&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;totalAmount&quot;: 1,
        &quot;successAmount&quot;: 0,
        &quot;failAmount&quot;: 1,
        &quot;failDetails&quot;: [
            {
                &quot;id&quot;: &quot;5695695109488645671&quot;,
                &quot;code&quot;: 60005,
                &quot;msg&quot;: &quot;material not found&quot;
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

### Failure Details &lt;FailDetails&gt;

| Parameter Name | Type              | Description          |
| ------------ | ---------- | ------------ |
| code           | integer | Error code  |
| id             | string  | Tag ID     |
| msg            | string  | Error msg   |

## Error Codes

Below are specific error codes for the API. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 60005  | material not found |








