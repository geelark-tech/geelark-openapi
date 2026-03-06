## 请求URL

- `https://openapi.geelark.cn/open/v1/rpa/task/tiktokMessageAsia`


## 请求方法
- POST

## 请求参数

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| name | 否 |string| 任务名称，最多128字 |
| remark | 否 |string| 备注，最多200字 |
| scheduleAt | 是 |int| 计划时间（时间戳）|
| id | 是 |string|云手机id |
| usernames | 是 |array[string]|用户名 |
| content | 是 |string|内容，最多6000个字符 |

## 请求示例

```json
{
  "name":"test",
  "remark":"test remark",
  "scheduleAt": 1741846843,
  "id":"557536075321468390",
  "usernames":["user"],
  "content": "123456"
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