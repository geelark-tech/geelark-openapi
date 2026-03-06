[TOC]

## API Description
- Get the cloud phone device ID (please re-obtain the latest ID after one-click new phone), which corresponds to the cloud phone&#039;s unique hardware device ID, which is equivalent to the system&#039;s Andorid_ID. The App can bind to the cloud phone environment by obtaining this ID on the cloud phone. How to obtain the device ID on the App side:
Android 13 system: execute the getprop ro.boot.serialno command through adb
Other systems: execute the getprop ro.serialno command through adb

```java
if(android.os.Build.VERSION.SDK_INT == 33){
   serialNo = Command.exeCommand(&quot;getprop ro.boot.serialno&quot;);
}else {
   serialNo = Command.exeCommand(&quot;getprop ro.serialno&quot;);
}
```

## Request URL

- `https://openapi.geelark.com/open/v1/phone/serialNum/get`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | clound phone id | Refer to request example  |

## Request Example
```json
{
    &quot;id&quot;: &quot;528715748189668352&quot;
}
```

## Response Example

```json
{
    &quot;traceId&quot;: &quot;89D8C3C08DA4DB5089069D34A3786494&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;serialNum&quot;: &quot;r2cbvzlx5bs&quot;
    }
}
```

## Response Data Description

| Parameter Name | Type | Description |
| ----------- | -----------|----------- |
| serialNum | string | cloud phone device ID |

## Error Codes


The following are specific error codes for this API. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes)


| Error Code | Description |
| --- | --- |
| 42001 | Cloud phone does not exist |
