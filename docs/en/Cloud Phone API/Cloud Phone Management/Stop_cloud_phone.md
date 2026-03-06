[TOC]

## API Description

Batch shut down cloud phones.

## Request URL

*   `https://openapi.geelark.com/open/v1/phone/stop`

## Request Method

*   POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| ids | Yes | array\[string\] | List of cloud phone IDs | See request example |

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

## Response Data Description

| Parameter Name | Type | Description |
| --- | --- | --- |
| totalAmount | integer | Total number of requested IDs |
| successAmount | integer | Number of successfully shut down IDs |
| failAmount | integer | Number of failed IDs |
| failDetails | array\[FailDetails\] | Information about failures |

### failDetails Failure Information &lt;FailDetails&gt;

| Parameter Name | Type | Description |
| --- | --- | --- |
| code | integer | Error code |
| id | integer | Cloud phone ID |
| msg | string | Error message |

## Error Codes

Below are specific error codes for this interface. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 42001 | Cloud phone does not exist |
| 43005 | Cloud phone is executing a task |
| 43006 | Cloud phone is being remotely connected |