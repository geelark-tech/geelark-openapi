## 接口说明

查询并返回指定环境的 cookies，单次只能查询 1 个环境。


## 请求URL

- `http://localhost:40185/api/v1/browser/getCookie`

## 请求方法


- POST






## 请求参数


| 参数名 | 必选 | 类型 |  示例 | 说明
| --- | --- | --- | --- | --- |
| id | 是 | string | "123456789" |浏览器id|


## 请求示例


```json
{
    "id": "123456789",
}
```


## 响应示例


```json
{
    "traceId": "123456ABCDEF",
    "code": 0,
    "msg": "success",
    "data": {
        "cookies": "[]",
    }
}
```