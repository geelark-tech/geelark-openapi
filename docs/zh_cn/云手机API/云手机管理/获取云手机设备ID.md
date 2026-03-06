## 接口说明

- 获取云手机设备ID （一键新机后请重新获取最新的ID），对应云手机唯一的硬件设备ID，等同于系统的Andorid_ID，App可以通过在云手机上获取此ID与云手机环境绑定。App端获取设备ID方式：
Android 13系统：通过adb执行 getprop ro.boot.serialno 命令
其他系统：通过adb执行 getprop ro.serialno 命令

```java
if(android.os.Build.VERSION.SDK_INT == 33){
   serialNo = Command.exeCommand("getprop ro.boot.serialno");
}else {
   serialNo = Command.exeCommand("getprop ro.serialno");
}
```

## 请求URL

- `https://openapi.geelark.cn/open/v1/phone/serialNum/get`

## 请求方法

- POST

## 请求参数

| 参数名 | 必选 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- | --- |
| id | 是 | string | 云手机id | 526209711930868736 |

## 请求示例

```json
{
    "id" : "544932706425791985"
}
```


## 响应示例

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
## 响应体数据说明

| 参数名       |     类型   |    说明    |
| ----------- | -----------|----------- |
| serialNum | string | 设备id |

## 错误码


以下为接口特定错误码，其他错误码请参考[云手机错误码](https://open.geelark.cn/api/cloud-phone-error-codes)


| 错误码 | 说明 |
| --- | --- |
| 42001 | 云手机不存在 |


