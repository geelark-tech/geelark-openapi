[TOC]

## 请求URL

- `https://openapi.geelark.cn/open/v1/rpa/task/instagramPubReels`


## 请求方法
- POST

## 请求参数

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| name | 否 |string| 任务名称，最多128字 |
| remark | 否 |string| 备注，最多200字 |
| scheduleAt | 是 |int| 计划时间（时间戳）|
| id | 是 |string|云手机id |
| description | 是 |string|文案，最多2200字 |
| video | 是 |[]string|视频，最多10个视频，上传视频请参考 [上传临时文件到GeeLark](https://open.geelark.cn/api/upload-getUrl) |
| sameStyleUrl | 否 | string | 同款URL |
| sameStyleVoice | 否 | int | 同款音量，范围是0-100 |
| originalVoice | 否 | int | 原声音量，范围是0-100 |
| aiTag | 否 | bool | AI标签，默认为false |

## 请求示例
```json
{
 "name":"test",
 "remark":"test remark",
 "scheduleAt": 1741846843,
 "id":"557536075321468390",
 "description":"description",
 "video": ["https://material.geelark.cn/a.mp4"]
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