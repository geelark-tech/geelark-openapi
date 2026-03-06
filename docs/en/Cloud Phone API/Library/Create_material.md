## Interface Description
create material

## Request URL

- `https://openapi.geelark.com/open/v1/material/create`

## Request Method


- POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| url | Yes | string | please refer to [Upload temporary files to GeeLark](https://open.geelark.com/api/upload-getUrl)   | Refer to Request Example |
| tagsId | No | array[string] | tags id | Refer to Request Example |
| fileName | No | string | file name, up to 200 characters  | Refer to Request Example |


## Request Example
```json
{
 "url" : "https://material.geelark.cn/client-img/banner0903_cn.gif",
 "tagsId" : ["569577509402731994","569577514586891738"],
 "fileName": "a.jpg"
}
```


## Response Example

```json
{
 "traceId": "ADD9A7489BB2198DBC0FB37082684CB0",
 "code": 0,
 "msg": "success",
 "data": {
 "id": "570606523940605924",
 "failDetails": [
 {
 "id": "5695775094027319941",
 "code": 43022,
 "msg": "tag not found"
 }
 ]
 }
}
```

## Response Data Description

| Parameter Name | Type | Description |
| ----------- | -----------|----------- |
| id | string | material id |
| failDetails | array[FailDetails] | Failure details |

### Failure Details &lt;FailDetails&gt;

| Parameter Name | Type | Description |
| ------------ | ---------- | ------------ |
| code | integer | Error code |
| id | string | Tag ID |
| msg | string | Error msg |

## Error Codes

Below are specific error codes for the API. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 60001 | the material library has reached its maximum capacity |
| 60003 | illegal url，please upload temporary files to GeeLark and get the url |
| 60004 | The file format is not supported |
| 43022  | tag not found |
| 40005  | The resource does not exist. Please check if the URL resource is available |







