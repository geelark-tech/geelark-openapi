## 接口说明

获取ADB信息

## 请求URL

- `https://openapi.geelark.cn/open/v1/adb/getData`

## 请求方法

- POST


## 鉴权

所有请求均为 `POST`，请求头需设置 `Content-Type: application/json`。

必需请求头：

- `traceId`：Version 4 UUID（建议大写）
- **Token 模式：** `Authorization: Bearer YOUR_API_TOKEN`
- **Key 模式：** `appId`、`traceId`、`ts`、`nonce`、`sign`（见 [接口调用说明](../../使用指南/云手机/接口调用说明.md)）

## 请求参数

| 参数名 | 必选 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- | --- |
| ids | 是 | array[string] | 云手机id数组，最多200个 | ["526209711930868736"] |

## 请求示例

```json
{
 "ids" : ["526806961778328576","524798337208026112","524783756767134720"]
}
```


## 响应示例

```json
{
    "traceId": "8AB9D6B482B679ECB5578314903B80B9",
    "code": 0,
    "msg": "success",
    "data": {
        "items": [
            {
                "code": 0,
                "id": "524783756767134720",
                "ip": "124.71.210.176",
                "pwd": "8c1da4",
                "port": "25219"
            },
            {
                "code": 42002,
                "id": "524798337208026112",
                "ip": "",
                "pwd": "",
                "port": ""
            }
        ]
    }
}
```
## 响应体数据说明
### items
| 参数名       |     类型   |    说明    |
| ----------- | -----------|----------- |
| code | integer   | 错误码0 则是正常；其他看错误码表  |
| id | string   | 云手机id  |
| ip | string   | 连接ip  |
| port | string   | 端口  |
| pwd | string   | 用于glogin认证的密码  |


## 错误码

以下为接口特定错误码，其他错误码请参考[云手机错误码](../../错误码/云手机错误码.md)

| 错误码 | 说明 |
| --- | --- |
| 42001 | 云手机不存在 |
| 42002 | 云手机不处于运行状态 |
| 49001 | adb未开启 |
| 49002 | 机型暂不支持adb |