## 请求URL

- `https://openapi.geelark.cn/open/v1/rpa/task/instagramEdit`


## 请求方法
- POST

## 请求参数

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| name | 否 |string| 任务名称，最多128字 |
| remark | 否 |string| 备注，最多200字 |
| scheduleAt | 是 |int| 计划时间（时间戳）|
| id | 是 |string|云手机id |
| profilePicture | 否 | array[string] | 头像 |
| nickname | 否 | string | 昵称 |
| username | 否 | string | 用户名 |
| biography | 否 | string | 简介 |
| linkURL | 否 | string | 链接URL |
| linkTitle | 否 | string | 链接标题 |

## 请求示例
```json
{
 "name":"test",
 "remark":"test remark",
 "scheduleAt": 1741846843,
 "id":"557536075321468390",
 "nickname":"myName",
 "username": "myName"
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