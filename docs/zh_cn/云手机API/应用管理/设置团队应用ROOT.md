[TOC]

## 接口说明

开启或关闭团队应用ROOT

## 请求URL

- `https://openapi.geelark.cn/open/v1/app/root`

## 请求方法

- POST

## 请求参数

| 参数名 | 必选 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- | --- |
| id | 是 | string | 团队应用id | 497652752864775437 |
| opera | 是 | integer | 操作，0关闭，1打开 | 1 |

## 请求示例

```json
{
 &quot;id&quot;: &quot;497652752864775437&quot;,
 &quot;opera&quot;: 1
}
```

## 响应示例

```json
{
 &quot;traceId&quot;: &quot;886A92FCBE9B7A52A7F583FCBD2BF6A8&quot;,
 &quot;code&quot;: 0,
 &quot;msg&quot;: &quot;success&quot;
}
```

## 错误码

请参考[云手机错误码](https://open.geelark.cn/api/cloud-phone-error-codes)
