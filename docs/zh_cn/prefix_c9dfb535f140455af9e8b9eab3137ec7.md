[TOC]

## 请求URL

- `https://openapi.geelark.cn/open/v1/phone/importContacts`


## 请求方法
- POST

## 请求参数

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| id | 是 |string|云手机id |
| contacts | 是 | array[ContactObject] | 联系人信息数组 |

### 联系人信息 - ContactObject

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
|email1|否|string|邮件1|
|email2|否|string|邮件2|
|fax|否|string|传真号，手机号、工作手机和传真号必须至少有一个非空|
|firstName|否|string|名，姓和名必须至少有一个非空|
|lastName|否|string|姓，姓和名必须至少有一个非空|
|mobile|否|string|手机号，手机号、工作手机和传真号必须至少有一个非空|
|work|否|string|工作手机，手机号、工作手机和传真号必须至少有一个非空|

## 请求示例
```json
{
	"id":"557536075321468390",
	"contacts": [
		{
			"firstName": "jay",
			"mobile": "13288888888"
		}
	]
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

## 响应体数据说明

| 参数名       |     类型   |    说明    |
| ----------- | -----------|----------- |
| taskId | string | 任务id（任务生成后一小时后查询有效）|