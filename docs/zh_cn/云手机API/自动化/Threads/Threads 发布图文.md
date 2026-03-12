## 请求URL

- `https://openapi.geelark.cn/open/v1/rpa/task/threadsImage`


## 请求方法
- POST

## 请求参数

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| name | 否 |string| 任务名称，最多128字 |
| remark | 否 |string| 备注，最多200字 |
| scheduleAt | 是 |int| 计划时间（时间戳）|
| id | 是 |string|云手机id |
| topic | 否 | string |主题 |
| title | 是 |string|标题，最多500个字符|
| images | 是 |[]string|图片，上传图片请参考 [上传临时文件到GeeLark](https://open.geelark.cn/api/upload-getUrl)  |

## 请求示例
```json
{
 "name":"test",
 "remark":"test remark",
 "scheduleAt": 1741846843,
 "id":"557536075321468390",
 "title": "title",
 "images": ["https://material.geelark.cn/a.jpg"]
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