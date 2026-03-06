[TOC]

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
 &quot;url&quot; : &quot;https://material.geelark.cn/client-img/banner0903_cn.gif&quot;,
 &quot;tagsId&quot; : [&quot;569577509402731994&quot;,&quot;569577514586891738&quot;],
 &quot;fileName&quot;: &quot;a.jpg&quot;
}
```


## Response Example

```json
{
 &quot;traceId&quot;: &quot;ADD9A7489BB2198DBC0FB37082684CB0&quot;,
 &quot;code&quot;: 0,
 &quot;msg&quot;: &quot;success&quot;,
 &quot;data&quot;: {
 &quot;id&quot;: &quot;570606523940605924&quot;,
 &quot;failDetails&quot;: [
 {
 &quot;id&quot;: &quot;5695775094027319941&quot;,
 &quot;code&quot;: 43022,
 &quot;msg&quot;: &quot;tag not found&quot;
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







