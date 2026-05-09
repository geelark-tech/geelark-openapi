## 请求URL

- `https://openapi.geelark.cn/open/v1/rpa/task/facebookReelsActive`


## 请求方法
- POST

## 请求参数

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| name | 否 |string| 任务名称，最多128字 |
| remark | 否 |string| 备注，最多200字 |
| scheduleAt | 是 |integer| 计划时间（时间戳）|
| id | 是 |string|云手机id |
| videoNumber | 是 |integer|预计浏览视频数量 |
| searchKeywords | 否 |array[string]|搜索关键字|

## 请求示例

```json
{
  "name":"test",
  "remark":"test remark",
  "scheduleAt": 1741846843,
  "id":"557536075321468390",
  "videoNumber":10,
  "searchKeywords": ["hello"]
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