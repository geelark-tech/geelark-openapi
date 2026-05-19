## 请求URL

- `https://openapi.geelark.cn/open/v1/rpa/task/tiktokEdit`


## 请求方法
- POST


## 鉴权

所有请求均为 `POST`，请求头需设置 `Content-Type: application/json`。

必需请求头：

- `traceId`：Version 4 UUID（建议大写）
- **Token 模式：** `Authorization: Bearer YOUR_API_TOKEN`
- **Key 模式：** `appId`、`traceId`、`ts`、`nonce`、`sign`（见 [接口调用说明](../../../使用指南/云手机/接口调用说明.md)）

## 请求参数

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| name | 否 |string| 任务名称，最多128字 |
| remark | 否 |string| 备注，最多200字 |
| scheduleAt | 是 |integer| 计划时间（时间戳）|
| id | 是 |string|云手机id |
| avatar | 否 |string|头像url ，请参考 [上传临时文件到GeeLark](https://open.geelark.cn/api/upload-getUrl)，上传的图片宽高比例1:1，否则会编辑失败|
|nickName|否|string|昵称，最多30字|
|bio|否|string|简介，最多160字|
|site|否|string|网站，请输入http/https开头的url链接|

## 请求示例
```json
{
 "name":"test",
 "remark":"test remark",
 "scheduleAt": 1741846843,
 "id":"557536075321468390",
 "avatar":"https://singapore-upgrade.geelark.cn/a.jpg",
 "nickName": "test",
 "bio":"test",
 "site":"https://www.abc.com" 
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

## 相关接口

- [查询任务](../任务管理/查询任务.md)
- [查询任务详情](../任务管理/查询任务详情.md)
- [取消任务](../任务管理/取消任务.md)

## 错误码

请参阅 [云手机错误码](../../../错误码/云手机错误码.md)；接口特定错误码亦可能出现在响应的 `code` / `msg` 字段中。
