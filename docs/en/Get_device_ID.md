## API Description
- Get the cloud phone device ID (please re-obtain the latest ID after one-click new phone), which corresponds to the cloud phone's unique hardware device ID, which is equivalent to the system's Andorid_ID. The App can bind to the cloud phone environment by obtaining this ID on the cloud phone. How to obtain the device ID on the App side:
Android 13 system: execute the getprop ro.boot.serialno command through adb
Other systems: execute the getprop ro.serialno command through adb

```java
if(android.os.Build.VERSION.SDK_INT == 33){
   serialNo = Command.exeCommand("getprop ro.boot.serialno");
}else {
   serialNo = Command.exeCommand("getprop ro.serialno");
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
    "id": "528715748189668352"
}
```

## Response Example

```json
{
    "traceId": "89D8C3C08DA4DB5089069D34A3786494",
    "code": 0,
    "msg": "success",
    "data": {
        "serialNum": "r2cbvzlx5bs"
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
