## 请求URL

- `https://openapi.geelark.cn/open/v1/rpa/task/tiktokRandomCommentAsia`


## 请求方法
- POST

## 请求参数

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| name | 否 |string| 任务名称，最多128字 |
| remark | 否 |string| 备注，最多200字 |
| scheduleAt | 是 |int| 计划时间（时间戳）|
| id | 是 |string|云手机id |
| useAi | 是 |int|是否使用ai；1 ai(仅pro用户可用); 2 不是ai，自己传评论 |
| comment | 是 |string|评论内容，最多500字，useAi为 2 时必传 |
| links | 否 | array[string] | 指定链接 |
| commentProbability | 否 |int|评论概率，0-100，默认为30|

## 请求示例
```json
{
 "name":"test",
 "remark":"test remark",
 "scheduleAt": 1741846843,
 "id":"557536075321468390",
 "useAi":2,
 "comment": "test"
}
```

## 响应示例

```json
{
    "traceId": "A4D8BCF69B878A71AC589F5CB1D80EAB",
    "code": 0,
    "msg": "success",
    "data": {
        "taskId": "558017255909123564"
    }
}
```