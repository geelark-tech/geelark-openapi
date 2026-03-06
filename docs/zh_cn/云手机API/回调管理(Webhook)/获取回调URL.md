[TOC]

## 接口说明
获取用户设置的回调接口URL


## 请求URL

- `https://openapi.geelark.cn/open/v1/callback/get`

## 请求方法

- POST


## 响应示例

```json
{
    &quot;traceId&quot;: &quot;9CEA6CC9B5BB68BBAE4ABDF9BE5AC89D&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;url&quot;: &quot;http:/example.geelark.com/phone/callback/test&quot;
    }
}
```

## 响应体数据说明

| 参数名       |     类型   |    说明    |
| ----------- | -----------|----------- |
| url | string | 设置的回调url |

## 错误码

以下为接口特定错误码，其他错误码请参考[云手机错误码](https://open.geelark.cn/api/cloud-phone-error-codes)

| 错误码 | 说明 |
| --- | --- |
| 51001 | 未设置回调url |






