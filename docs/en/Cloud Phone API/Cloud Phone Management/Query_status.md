[TOC]

## API Description

Retrieve the status of cloud phones.

## Request URL

*   `https://openapi.geelark.com/open/v1/phone/status`

## Request Method

*   POST

## Request Parameters

### Query Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| ids | Yes | array\[string\] | List of cloud phone IDs, Limit to 100 elements | See request example |

## Request Example

```json
{
    &quot;ids&quot;:[
        &quot;123456ABCDEF&quot;,
        &quot;123456ABCDEF&quot;,
        &quot;123456ABCDEF&quot;,
        &quot;123456ABCDEF&quot;
    ]
}
```

## Response Data Description

| Parameter Name | Type | Description |
| --- | --- | --- |
| totalAmount | integer | Total number of requested IDs |
| successAmount | integer | Total number of successful responses |
| failAmount | integer | Total number of failed responses |
| successDetails | array\[SuccessDetails\] | Information about successful responses |
| failDetails | array\[FailDetails\] | Information about failed responses |

### successDetails Success Information &lt;SuccessDetails&gt;

| Parameter Name | Type | Description |
| --- | --- | --- |
| id | string | ID of the successful cloud phone |
| serialName | string | Name of the successful cloud phone |
| status | integer | Cloud phone status code&lt;br/&gt; 0 - Started&lt;br/&gt; 1 - Starting&lt;br/&gt; 2 - Shut down&lt;br/&gt; 3 - Expired |

### failDetails Failure Information &lt;FailDetails&gt;

| Parameter Name | Type | Description |
| --- | --- | --- |
| code | int | Failure code 42001: Cloud phone does not exist |
| id | string | ID of the failed cloud phone |
| msg | string | Failure message |

## Response Example

```json
{
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;成功&quot;,
    &quot;traceId&quot;: &quot;123456ABCDEF&quot;,
    &quot;data&quot;: {
        &quot;totalAmount&quot;: 4,
        &quot;successAmount&quot;: 3,
        &quot;failAmount&quot;: 1,
        &quot;successDetails&quot;: [
            {
                &quot;id&quot;: &quot;123456ABCDEF&quot;,
                &quot;serialName&quot;: &quot;name1&quot;,
                &quot;status&quot;: 0
            },
            {
                &quot;id&quot;: &quot;123456ABCDEF&quot;,
                &quot;serialName&quot;: &quot;name2&quot;,
                &quot;status&quot;: 1
            },
            {
                &quot;id&quot;: &quot;123456ABCDEF&quot;,
                &quot;serialName&quot;: &quot;name3&quot;,
                &quot;status&quot;: 1
            }
        ],
        &quot;failDetails&quot;: [
            {
                &quot;code&quot;: 42001,
                &quot;id&quot;: &quot;123456ABCDEF&quot;,
                &quot;msg&quot;: &quot;env not found&quot;
            }
        ]
    }
}
```

## Error Codes

Below are specific error codes for this interface. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 42001 | Cloud phone does not exist |