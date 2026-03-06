[TOC]

## 接口说明

- 设置ROOT状态，在打开ROOT前，请先启动云手机

## 请求URL

- `https://openapi.geelark.cn/open/v1/root/setStatus`

## 请求方法

- POST

## 请求参数

| 参数名 | 必选 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- | --- |
| ids | 是 |array[string] | 云手机环境id数组（仅支持安卓12、13、14、15类型的机器，不支持的机型会自动过滤） | 526209711930868736 |
| open | 是 | bool | 打开/关闭 | false |

## 请求示例

```json
{
    &quot;ids&quot; : [
        &quot;526209711930868736&quot;
    ],
    &quot;open&quot; : true
}
```


## 响应示例

```json
{
    &quot;traceId&quot;: &quot;A24A3089958A4BC28E8B89B3AE1A61AC&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
	&quot;data&quot;: {
        &quot;items&quot;: [
            {
                &quot;code&quot;: 42002,
                &quot;msg&quot;: &quot;phone is not running&quot;,
                &quot;id&quot;: &quot;543483007558772199&quot;
            },
            {
                &quot;code&quot;: 0,
                &quot;msg&quot;: &quot;success&quot;,
                &quot;id&quot;: &quot;543483063829554663&quot;
            }
        ]
    }
}
```

## 错误码


以下为接口特定错误码，其他错误码请参考[云手机错误码](https://open.geelark.cn/api/cloud-phone-error-codes)


| 错误码 | 说明 |
| --- | --- |
| 42001 | 云手机不存在 |
| 42002 | 云手机不在运行状态 |
| 43016 | 云手机暂不支持root |


