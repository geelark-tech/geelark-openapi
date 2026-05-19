## 接口说明

用于检查当前设备API接口的可用性


## 请求URL

- `http://localhost:40185/api/v1/status`

## 请求方法


- POST







## 鉴权

所有请求均为 `POST`，请求头需设置 `Content-Type: application/json`。

必需请求头：

- `traceId`：Version 4 UUID（建议大写）
- **Token 模式：** `Authorization: Bearer YOUR_API_TOKEN`
- **Key 模式：** `appId`、`traceId`、`ts`、`nonce`、`sign`（见 [接口调用说明](../../使用指南/浏览器/接口调用说明.md)）

## 响应示例


```json
{
    "code": 0,
    "msg": "success"
}
```


## 错误码


错误码请参考[浏览器错误码](../../错误码/浏览器错误码.md)