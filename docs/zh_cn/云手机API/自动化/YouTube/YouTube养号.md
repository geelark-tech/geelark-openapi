[TOC]

## 请求URL

- `https://openapi.geelark.cn/open/v1/rpa/task/youTubeActiveAccount`


## 请求方法
- POST

## 请求参数

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| name | 否 |string| 任务名称，最多128字 |
| remark | 否 |string| 备注，最多200字 |
| scheduleAt | 是 |int| 计划时间（时间戳）|
| id | 是 |string|云手机id |
| browseVideoNum | 是 |int|预计浏览视频条数，最小值1，最大100 |
| keyword | 是 |[]string|关键词，最多10个，每个评论最多150字 |

## 请求示例
```json
{
 &quot;name&quot;:&quot;test&quot;,
 &quot;remark&quot;:&quot;test remark&quot;,
 &quot;scheduleAt&quot;: 1741846843,
 &quot;id&quot;:&quot;557536075321468390&quot;,
 &quot;postAddress&quot;:&quot;https://abc.com&quot;,
 &quot;browseVideoNum&quot;: 10,
 &quot;keyword&quot;: [&quot;k1&quot;, &quot;k2&quot;]
}
```

## 响应示例

```json
{
    &quot;traceId&quot;: &quot;A4D8BCF69B878A71AC589F5CB1D80EAB&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;taskId&quot;: &quot;558017255909123564&quot;
    }
}
```