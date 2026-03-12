## 请求URL

- `https://openapi.geelark.cn/open/v1/rpa/task/tiktokEdit`


## 请求方法
- POST

## 请求参数

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| name | 否 |string| 任务名称，最多128字 |
| remark | 否 |string| 备注，最多200字 |
| scheduleAt | 是 |int| 计划时间（时间戳）|
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