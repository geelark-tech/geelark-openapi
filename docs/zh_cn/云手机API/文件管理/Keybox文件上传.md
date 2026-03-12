## 接口说明

上传Keybox文件，通过Google完整性验证，目前仅支持Android 12/13/15系统版本。Android 12/13只需上传Keybox文件即可，Android 15需要以下额外步骤：
1、更新最新的Google Play、GMS
2、登陆有效的Google账户
3、从Google Play下载Play Integrity API Checker

## 请求 URL


- `https://openapi.geelark.cn/open/v1/phone/keyboxUpload`


## 请求方法


- POST


## 请求参数


| 参数名      | 必选 | 类型          | 说明                 |
| ----------- | ---- | ------------- | -------------------- |
| id          | 是   | string        | 云手机 id            |
| fileUrl          | 是   | string        | 文件链接           |


## 请求示例


```json
{
  "id":"572036556940928503",
  "fileUrl":"https://material.geelark.cn/client-img/oakendn.xml"
}
```


## 响应示例


```json
{
    "traceId": "9738691CA8A3589D8822A11FAE2B2A9A",
    "code": 0,
    "msg": "success",
    "data": {
        "taskId": "1957394823745384448"
    }
}
```

## 响应体数据说明
| 参数名       |     类型   |    说明    |
| ----------- | -----------|----------- |
| taskId | string | 任务id |

## 错误码


以下为接口特定错误码，其他错误码请参考[云手机错误码](https://open.geelark.cn/api/cloud-phone-error-codes)

| 错误码 | 说明                         |
| ------ | ---------------------------- |
| 42001  | 云手机不存在                 |
| 42002  | 云手机不运行中                 |
| 43026  | 云手机系统不支持                |
| 60003  | 非法文件链接                |