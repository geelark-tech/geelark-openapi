[TOC]

API Description
-----------------

Batch Delete Cloud Phones

Request URL
-----------

* `https://openapi.geelark.com/open/v1/phone/delete`

Request Method
--------------

* POST

Request Parameters
------------------

| Parameter | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| ids | Yes | array\[string\] | List of cloud phone IDs, Limit to 100 elements | Refer to the request example |

Request Example
---------------
```json
{
    &quot;ids&quot;:[
        &quot;123456ABCDEF&quot;,
        &quot;123456ABCDEF&quot;
    ]
}
```

Response Data Description
-------------------------

| Parameter | Type | Description |
| --- | --- | --- |
| totalAmount | integer | Total number of requested IDs |
| successAmount | integer | Total number of successful IDs |
| failAmount | integer | Total number of failed IDs |
| failDetails | array\[FailDetails\] | Failure details |

### Failure Details &lt;FailDetails&gt;

| Parameter | Type | Description |
| --- | --- | --- |
| code | integer | Error code |
| id | integer | Cloud phone ID |
| msg | string | Error message |

Response Example
----------------

```json
{
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;traceId&quot;: &quot;12345ABCDEF&quot;,
    &quot;data&quot;: {
        &quot;totalAmount&quot;: 4,
        &quot;successAmount&quot;: 2,
        &quot;failAmount&quot;: 2,
        &quot;failDetails&quot;: [
            {
                &quot;code&quot;: 42001,
                &quot;id&quot;: &quot;12345ABCDEF&quot;,
                &quot;msg&quot;: &quot;env not found&quot;
            },
            {
                &quot;code&quot;: 43009,
                &quot;id&quot;: &quot;12345ABCDEF&quot;,
                &quot;msg&quot;: &quot;env is started&quot;
            }
        ]
    }
}
```

Error Codes
-----------

Below are specific error codes for the API. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 42001 | Cloud phone does not exist |
| 43009 | Cloud phone is started, cannot delete |
| 43010 | Cloud phone is starting, cannot delete |
| 43021 | The cloud phone is in use, please try again later |
