[TOC]


## 接口说明

创建充值订单，返回支付二维码的url，可在浏览器打开扫码充值

## 请求URL

- `https://openapi.geelark.cn/open/v1/pay/wallet/recharge`

## 请求方法

- POST

## 请求参数

| 参数名       | 必选   |     类型   |    说明    |示例|
| ----------- | -------| -----------|----------- |--------- |
| payChannel   | 是     |   int | 支付方式 | 目前支持：1支付宝 2微信 |
|payNum|是|int|支付金额(美金)|充值数量$100起步，必须是$100的整数，且少于$5000|

## 请求示例

```json
{
 "payChannel":1,
 "payNum": 200
}
```

## 响应体数据说明

| 参数名       |     类型   |    说明    |
| ----------- | -----------|----------- |
| orderId | string   | 订单号 |
| url  | string    | 支付二维码 |

## 响应示例

```json
{
    "traceId": "B2094CC984AA5B4485E0948DAABB478B",
    "code": 0,
    "msg": "success",
    "data": {
        "orderId": "553338482326375364",
        "url": "https://material.geelark.cn/openapi/recharge/20250212/233333.png"
    }
}
```

