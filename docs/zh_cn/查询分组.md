[TOC]

## 接口说明


- 获取分组信息


## 请求 URL


- `https://openapi.geelark.cn/open/v1/group/list`


## 请求方法


- POST


## 请求参数


### 分页参数


| 参数名       | 必选   |     类型    |     说明                             | 示例 |
| ------------ | ------ | ----------- | ------------------------------------ | ---- |
| page         | 是     |   integer   | 页码，最小为 1                       | 1    |
| pageSize     | 是     |   integer   | 每页多少条数据，最小为 1，最大为 100 | 10   |


### 查询参数


| 参数名  | 必选 | 类型          | 说明         | 示例         |
| ------- | ---- | ------------- | ------------ | ------------ |
| ids     | 否   | array[string] | 分组 id 列表 | 参考请求示例 |
| names   | 否   | array[string] | 分组名字列表 | 参考请求示例 |
| remarks | 否   | array[string] | 分组颜色列表 | 参考请求示例 |


## 请求示例


### 不携带查询条件


```json
{
  "page": 1,
  "pageSize": 5
}
```


### 根据 ids 查询


```json
{
  "page": 1,
  "pageSize": 5,
  "ids": ["528995439832269824", "528985080069096448"]
}
```


### 根据 names 查询


```json
{
  "page": 1,
  "pageSize": 5,
  "names": ["groupRemark", "testRemark"]
}
```


### 根据 remarks 查询


```json
{
  "page": 1,
  "pageSize": 5,
  "remarks": ["remark", "test"]
}
```


## 响应示例


```json
{
  "traceId": "A25B0025BA886B1EB2679AAAAC599998",
  "code": 0,
  "msg": "success",
  "data": {
    "total": 2,
    "page": 1,
    "pageSize": 5,
    "list": [
      {
        "id": "528995439832269824",
        "name": "groupRemark",
        "remark": "remark"
      },
      {
        "id": "528985080069096448",
        "name": "testRemark",
        "remark": "test"
      }
    ]
  }
}
```


## 响应体数据说明


| 参数名       |     类型           |     说明     |
| ------------ | ------------------ | ------------ |
| total        | integer            | 总数         |
| page         | integer            | 页码         |
| pageSize     | integer            | 分页大小     |
| list         | array[Group]       | 分组列表     |
| failDetails  | array[FailDetails] | 失败信息     |


### list 分组列表 <Group>


| 参数名 | 类型   | 说明     |
| ------ | ------ | -------- |
| id     | string | 分组 id  |
| name   | string | 分组名   |
| remark | string | 分组备注 |


### failDetails 失败信息 <FailDetail>


| 参数名 | 类型    | 说明                                    |
| ------ | ------- | --------------------------------------- |
| code   | integer | 错误码                                  |
| type   | integer | 失败类型：1-分组id 2-分组名 3-分组标签 |
| param  | string  | 失败参数                                |
| msg    | string  | 失败信息                                |


## 错误码


以下为接口特定错误码，其他错误码请参考[云手机错误码](https://open.geelark.cn/api/cloud-phone-error-codes)


| 错误码 | 说明           |
| ------ | -------------- |
| 43032  | 分组不存在     |
| 43033  | 分组名不存在   |  
| 43034  | 分组备注不存在 |                                                                                                                         