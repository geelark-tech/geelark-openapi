## 请求URL

- `http://localhost:40185/api/v1/browser/task/facebookPost`

## 请求方法

- POST

## 请求参数

| 参数名       | 必选   |     类型   |    说明    | 示例|
| ----------- | -------| -----------|----------- |----------- |
|eid|是|string|环境id|497652752864775437|
|name|否|string|任务名称，最多128字|myTask|
|remark|否|string|备注，最多200字|myRemark|
|scheduleAt|是|integer|计划时间，秒级时间戳|1741846843|
|content|是|string|内容|hello|


## 请求示例

```json
{
    "name":"test",
    "remark":"test remark",
    "scheduleAt": 1741846843,
    "eid":"557536075321468390",
	"content": "hello"
}
```

## 响应示例

```json
{
    "traceId": "A4D8BCF69B878A71AC589F5CB1D80EAB",
    "code": 0,
    "msg": "success",
    "data": {
        "taskId": "558017255909123564"
    }
}
```