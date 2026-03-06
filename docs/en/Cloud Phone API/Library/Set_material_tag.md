[TOC]

## Interface Description
set material tag

## Request URL

- `https://openapi.geelark.com/open/v1/material/tag/set`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type          | Description           | Example           |
| --- | --- | --- | --- | --- |
| materialsId | Yes | array[string] | material id | Refer to Request Example  |
| tagsId | No | array[string] | tags id，Each tagging operation will delete all existing tags and only retain the newly set tags | Refer to Request Example  |


## Request Example
```json
{
 &quot;materialsId&quot; : [&quot;570457374221926935&quot;],
 &quot;tagsId&quot; : [&quot;570461738663674391&quot;]
}
```


## Response Example

```json
{
    &quot;traceId&quot;: &quot;AC3ADD84BEA1D8D2A7DDAF8B90A8D2A8&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;failDetails&quot;: [
            {
                &quot;id&quot;: &quot;5704573742219269351&quot;,
                &quot;code&quot;: 60005,
                &quot;msg&quot;: &quot;material not found&quot;
            },
            {
                &quot;id&quot;: &quot;5704617386636743911&quot;,
                &quot;code&quot;: 43022,
                &quot;msg&quot;: &quot;tag not found&quot;
            }
        ]
    }
}
```

## Response Data Description
### failDetails Failure Info &lt;FailDetails&gt;


| Parameter Name | Type    | Description |
| -------------- | ------- | ----------- |
| code           | integer | Error code  |
| id             | string  | Tag ID      |
| msg            | string  | Error msg   |


## Error Codes

Below are specific error codes for the API. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 43022  | tag not found |
| 60005  | material not found |









