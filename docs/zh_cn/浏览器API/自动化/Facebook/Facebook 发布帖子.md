## 请求URL

- `http://localhost:40185/api/v1/browser/task/facebookPost`

## 请求方法

- POST


## 鉴权

所有请求均为 `POST`，请求头需设置 `Content-Type: application/json`。

必需请求头：

- `traceId`：Version 4 UUID（建议大写）
- **Token 模式：** `Authorization: Bearer YOUR_API_TOKEN`
- **Key 模式：** `appId`、`traceId`、`ts`、`nonce`、`sign`（见 [接口调用说明](../../../使用指南/浏览器/接口调用说明.md)）

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

## 相关接口

- [查询任务](../任务管理/查询任务.md)
- [查询任务详情](../任务管理/查询任务详情.md)
- [取消任务](../任务管理/取消任务.md)

## 错误码

请参阅 [云手机错误码](../../../错误码/浏览器错误码.md)；接口特定错误码亦可能出现在响应的 `code` / `msg` 字段中。
