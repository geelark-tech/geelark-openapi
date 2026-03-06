## 接口说明
在云手机上执行adb shell命令

- 只支持`Android10`、`Andriod12`、`Andriod13`、`Andriod14`、`Andriod15`机型

## 请求URL

- `https://openapi.geelark.cn/open/v1/shell/execute`

## 请求方法

- POST

## 请求参数

| 参数名 | 必选 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- | --- |
| id | 是 | string | 云手机id | 参考请求示例 |
| cmd | 是 | string | 执行的命令 | 参考请求示例 |


## 请求示例
```json
{
    "id": "528715748189668352",
    "cmd": "pm list packages"
}
```


## 响应示例

```json
{
    "traceId": "A619E93696ABFB81B7FCB9939DB8B49F",
    "code": 0,
    "msg": "success",
    "data": {
        "status": true,
        "output": "com.zhiliaoapp.musically"
    }
}
```

## 响应体数据说明

| 参数名       |     类型   |    说明    |
| ----------- | -----------|----------- |
| status | bool | true: 执行成功 false: 执行失败 |
| output | string | 执行结果 |

## 错误码

以下为接口特定错误码，其他错误码请参考[云手机错误码](https://open.geelark.cn/api/cloud-phone-error-codes)

| 错误码 | 说明 |
| --- | --- |
| 42001 | 云手机不存在 |
| 42002 | 云手机不处于运行状态 |
| 50001 | 云手机不支持shell命令 |






