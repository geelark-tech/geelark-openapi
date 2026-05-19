## 接口说明
设置回调URL后，可以在自己设置的回调接口中处理相关信息


## 请求URL

- `https://openapi.geelark.cn/open/v1/callback/set`

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
| url | 是 | string | 回调接口地址 | http:/example.geelark.com/phone/callback/test |


## 请求示例
```json
{
    "url": "http:/example.geelark.com/phone/callback/test"
}
```


## 响应示例

```json
{
    "traceId": "960B32039F84AA489514ADCC9ADA909F",
    "code": 0,
    "msg": "success"
}
```