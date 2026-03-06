[TOC]

## 接口说明

更换套餐，API只支持升级套餐，降级套餐请通过GeeLark客户端完成

## 请求URL

- `https://openapi.geelark.cn/open/v1/pay/plan/upgrade`

## 请求方法

- POST

## 请求参数

| 参数名       | 必选   |     类型   |    说明    |示例|
| ----------- | -------| -----------|----------- |--------- |
| profilesId   | 是     |   string  | 套餐id，可通过套餐列表接口获取 | 497540679501610040 |
|parallelsNum|是|int|并发数，需大于等于当前套餐的并发数| 1 |
|monthlyRentalNum|是|int|包月设备数，需大于等于当前套餐的包月设备数| 1  |
|promoCode|否|string|优惠码| PromoCode |
|days|否|int|套餐过期的情况下必传，续期时长：30/90/180/360 天| 30 |

## 请求示例

```json
{
    "profilesId": "497540679501610040",
    "parallelsNum":1,
    "monthlyRentalNum" : 1
}
```

## 响应示例

```json
{
    "traceId": "A3889654BA84B91CBABF8535B83AEABB",
    "code": 0,
    "msg": "success"
}
```

## 错误码

以下为接口特定错误码，其他错误码请参考[接口调用说明](https://open.geelark.cn/api/cloud-phone-error-codes)

| 错误码 | 说明 |
| --- | --- |
| 41001 | 余额不足 |
| 41002 | 仅支持升级套餐，请到客户端操作 |
| 41003 | 优惠码无效 |

