[TOC]

## 接口说明
用户请求api后，可以在自己设置的回调接口中处理相关信息


## 请求URL

- `https://openapi.geelark.cn/open/v1/callback/set`

## 请求方法

- POST

## 请求参数

| 参数名 | 必选 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- | --- |
| url | 是 | string | 回调接口地址 | http:/example.geelark.com/phone/callback/test |


## 请求示例
```json
{
    &quot;url&quot;: &quot;http:/example.geelark.com/phone/callback/test&quot;
}
```


## 响应示例

```json
{
    &quot;traceId&quot;: &quot;960B32039F84AA489514ADCC9ADA909F&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;
}
```








