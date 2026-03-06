[TOC]

API Description
---------------

Retrieve ADB Information

Request URL
-----------

* `https://openapi.geelark.com/open/v1/adb/getData`

Request Method
--------------

* POST

Request Parameters
------------------

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| ids | Yes | array\[string\] | Array of cloud phone IDs | \[&quot;526209711930868736&quot;\] |

Request Example
---------------

```json
{
 &quot;ids&quot; : [&quot;526806961778328576&quot;,&quot;524798337208026112&quot;,&quot;524783756767134720&quot;]
}
```


Response Data Description
-------------------------
### items
| Parameter Name | Type | Description |
| --- | --- | --- |
| code | int | Error code: 0 indicates success; for other codes, refer to the error code table |
| id | string | Cloud phone ID |
| ip | string | Connection IP |
| port | string | Port |
| pwd | string | Password |

Response Example
----------------

```json
{
    &quot;traceId&quot;: &quot;8AB9D6B482B679ECB5578314903B80B9&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;items&quot;: [
            {
                &quot;code&quot;: 0,
                &quot;id&quot;: &quot;524783756767134720&quot;,
                &quot;ip&quot;: &quot;124.71.210.176&quot;,
                &quot;pwd&quot;: &quot;8c1da4&quot;,
                &quot;port&quot;: &quot;25219&quot;
            },
            {
                &quot;code&quot;: 42002,
                &quot;id&quot;: &quot;524798337208026112&quot;,
                &quot;ip&quot;: &quot;&quot;,
                &quot;pwd&quot;: &quot;&quot;,
                &quot;port&quot;: &quot;&quot;
            }
        ]
    }
}
```

Error Codes
-----------

The following are specific error codes for this API. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 42001 | Cloud phone does not exist |
| 42002 | Cloud phone is not running |
| 49001 | ADB is not enabled |
| 49002 | The device does not support ADB |