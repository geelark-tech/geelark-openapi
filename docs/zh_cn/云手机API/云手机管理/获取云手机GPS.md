## 接口说明


- 查询云手机 GPS 信息，包含经纬度


## 请求 URL


- `https://openapi.geelark.cn/open/v1/phone/gps/get`


## 请求方法


- POST



## 鉴权

所有请求均为 `POST`，请求头需设置 `Content-Type: application/json`。

必需请求头：

- `traceId`：Version 4 UUID（建议大写）
- **Token 模式：** `Authorization: Bearer YOUR_API_TOKEN`
- **Key 模式：** `appId`、`traceId`、`ts`、`nonce`、`sign`（见 [接口调用说明](../../使用指南/云手机/接口调用说明.md)）

## 请求参数


| 参数名 | 必选 | 类型   | 说明      | 示例         |
| ------ | ---- | ------ | --------- | ------------ |
| ids     | 是   | array[string] | 云手机 id列表 | 参考请求示例 |


## 请求示例


```json
{
    "ids": [
        "528086321789535232"
    ]
}
```


## 响应示例


```json
{
    "traceId": "81CA3BD0B7BBB924A1C6B836B298ADA7",
    "code": 0,
    "msg": "success",
    "data": {
        "totalAmount": 1,
        "successAmount": 1,
        "failAmount": 0,
        "list": [
            {
                "id": "528086321789535232",
                "latitude": 1.3024300336837769,
                "longitude": 103.87545776367188
            }
        ]
    }
}
```


## 响应体数据说明

| 参数名       |     类型   |     说明     |
| ------------ | ---------- | ------------ |
| totalAmount | integer | 请求id总数 |
| successAmount | integer | 成功总数 |
| failAmount | integer | 失败总数 |
| list | GPS | gps信息 |

### list gps信息 <GPS>
| 参数名       |     类型   |     说明     |
| ------------ | ---------- | ------------ |
| id | string | 云手机id |
| latitude     | float      | 纬度         |
| longitude    | float      | 经度         |


## 错误码


以下为接口特定错误码，其他错误码请参考[云手机错误码](../../错误码/云手机错误码.md)


| 错误码 | 说明 |
| --- | --- |
| 42001 | 云手机不存在 |