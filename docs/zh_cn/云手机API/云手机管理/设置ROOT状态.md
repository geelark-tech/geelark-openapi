## 接口说明

- 设置ROOT状态，在打开ROOT前，请先启动云手机

## 请求URL

- `https://openapi.geelark.cn/open/v1/root/setStatus`

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
| ids | 是 |array[string] | 云手机环境id数组（仅支持安卓12、13、14、15、16类型的机器，不支持的机型会自动过滤） | 526209711930868736 |
| open | 是 | bool | 打开/关闭 | false |

## 请求示例

```json
{
    "ids" : [
        "526209711930868736"
    ],
    "open" : true
}
```


## 响应示例

```json
{
    "traceId": "A24A3089958A4BC28E8B89B3AE1A61AC",
    "code": 0,
    "msg": "success",
	"data": {
        "items": [
            {
                "code": 42002,
                "msg": "phone is not running",
                "id": "543483007558772199"
            },
            {
                "code": 0,
                "msg": "success",
                "id": "543483063829554663"
            }
        ]
    }
}
```

## 错误码


以下为接口特定错误码，其他错误码请参考[云手机错误码](../../错误码/云手机错误码.md)


| 错误码 | 说明 |
| --- | --- |
| 42001 | 云手机不存在 |
| 42002 | 云手机不在运行状态 |
| 43016 | 云手机暂不支持root |