## 接口说明

调用上传Keybox文件接口后，通过返回的taskId获取执行结果

## 请求 URL


- `https://openapi.geelark.cn/open/v1/phone/keyboxUpload/result`


## 请求方法


- POST



## 鉴权

所有请求均为 `POST`，请求头需设置 `Content-Type: application/json`。

必需请求头：

- `traceId`：Version 4 UUID（建议大写）
- **Token 模式：** `Authorization: Bearer YOUR_API_TOKEN`
- **Key 模式：** `appId`、`traceId`、`ts`、`nonce`、`sign`（见 [接口调用说明](../../使用指南/云手机/接口调用说明.md)）

## 请求参数


| 参数名      | 必选 | 类型          | 说明                 |
| ----------- | ---- | ------------- | -------------------- |
| id          | 是   | string        | 任务id            |


## 请求示例


```json
{
  "id":"1957625857585983488"
}
```


## 响应示例


```json
{
    "traceId": "A62B9AFFBA9869968572A2178CC91F88",
    "code": 0,
    "msg": "success",
    "data": {
        "status": 1
    }
}
```

## 响应体数据说明
| 参数名       |     类型   |    说明    |
| ----------- | -----------|----------- |
| status | integer | 任务状态 0正在执行；1执行成功；2执行失败 |

## 错误码

错误码请参考[云手机错误码](../../错误码/云手机错误码.md)