[TOC]


## 接口说明
 - 设置/更新云手机GPS信息，包括经度以及纬度
 - 经度取值范围：`[-180.0, 180.0]`
 - 纬度取值范围: `[-90.0, 90.0]`


## 请求URL


- `https://openapi.geelark.cn/open/v1/phone/gps/set`


## 请求方法


- POST


## 请求参数


| 参数名 | 必选 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- | --- |
| list | 是 | array[GPS] | 云手机GPS信息 | 参考请求示例 |

### list 云手机GPS信息 <GPS>
| 参数名 | 必选 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- | --- |
| id | 是 | string | 云手机id | 参考请求示例 |
| longitude | 是 | float | 经度 | 参考请求示例 |
| latitude | 是 | float | 纬度 | 参考请求示例 |


## 请求示例
```json
{
    "list": [
        {
            "id": "528086321789535232",
            "latitude": 1.30243,
            "longitude": 103.87546
        },
        {
            "id": "530011895768286208",
            "latitude": 11.30243,
            "longitude": 104.87546
        }
    ]
}
```



## 响应示例


```json
{
    "traceId": "870AE3259C965B45A0D09C92A4EA8F81",
    "code": 0,
    "msg": "success",
    "data": {
        "totalAmount": 2,
        "successAmount": 2,
        "failAmount": 0
    }
}
```
### 响应体数据说明

| 参数名       |     类型   |     说明     |
| ------------ | ---------- | ------------ |
| totalAmount | integer | 请求id总数 |
| successAmount | integer | 成功总数 |
| failAmount | integer | 失败总数 |

## 错误码


以下为接口特定错误码，其他错误码请参考[云手机错误码](https://open.geelark.cn/api/cloud-phone-error-codes)


| 错误码 | 说明 |
| --- | --- |
| 42001 | 云手机不存在 |
| 43012 | 经纬度范围错误 |








