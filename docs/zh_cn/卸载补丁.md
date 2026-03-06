[TOC]

## 接口说明

卸载补丁，目前只支持Android 12系统、Android 13系统、Android 15系统

## 请求URL

- `https://openapi.geelark.cn/open/v1/phone/patch/uninstall`

## 请求方法

- POST

## 请求参数

| 参数名 | 必选 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- | --- |
| patchId | 否 | string | 补丁id | "test" |
| id | 否 | string | 云手机id | 1830906144634757120 |

## 请求示例

```json
{
 "patchId": "sdktest",
 "id": "532930887177274368"
}
```

## 响应体数据说明

| 参数名       |     类型   |    说明    |
| ----------- | -----------|----------- |
| status | int | 状态 0失败；1成功|

## 响应示例

```json
{
    "traceId": "B9292502ADA00945BACF910EAB199F92",
    "code": 0,
    "msg": "success",
    "data": {
        "status": 1
    }
}
```

