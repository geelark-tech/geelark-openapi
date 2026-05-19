## 接口说明

查询并返回指定环境的 cookies，单次只能查询 1 个环境。


## 请求URL

- `http://localhost:40185/api/v1/browser/getCookie`

## 请求方法


- POST







## 鉴权

所有请求均为 `POST`，请求头需设置 `Content-Type: application/json`。

必需请求头：

- `traceId`：Version 4 UUID（建议大写）
- **Token 模式：** `Authorization: Bearer YOUR_API_TOKEN`
- **Key 模式：** `appId`、`traceId`、`ts`、`nonce`、`sign`（见 [接口调用说明](../../使用指南/浏览器/接口调用说明.md)）

## 请求参数


| 参数名 | 必选 | 类型 |  示例 | 说明
| --- | --- | --- | --- | --- |
| id | 是 | string | "123456789" |浏览器id|


## 请求示例


```json
{
    "id": "123456789",
}
```


## 响应示例


```json
{
    "traceId": "123456ABCDEF",
    "code": 0,
    "msg": "success",
    "data": {
        "cookies": "[]",
    }
}
```