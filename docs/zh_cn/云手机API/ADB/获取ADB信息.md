[TOC]

## 接口说明

获取ADB信息

## 请求URL

- `https://openapi.geelark.cn/open/v1/adb/getData`

## 请求方法

- POST

## 请求参数

| 参数名 | 必选 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- | --- |
| ids | 是 | array[string] | 云手机id数组 | [&quot;526209711930868736&quot;] |

## 请求示例

```json
{
 &quot;ids&quot; : [&quot;526806961778328576&quot;,&quot;524798337208026112&quot;,&quot;524783756767134720&quot;]
}
```


## 响应示例

```json
{
    &quot;traceId&quot;: &quot;8AB9D6B482B679ECB5578314903B80B9&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;items&quot;: [
            {
                &quot;code&quot;: 0,
                &quot;id&quot;: &quot;524783756767134720&quot;,
                &quot;ip&quot;: &quot;124.71.210.176&quot;,
                &quot;pwd&quot;: &quot;8c1da4&quot;,
                &quot;port&quot;: &quot;25219&quot;
            },
            {
                &quot;code&quot;: 42002,
                &quot;id&quot;: &quot;524798337208026112&quot;,
                &quot;ip&quot;: &quot;&quot;,
                &quot;pwd&quot;: &quot;&quot;,
                &quot;port&quot;: &quot;&quot;
            }
        ]
    }
}
```
## 响应体数据说明
### items
| 参数名       |     类型   |    说明    |
| ----------- | -----------|----------- |
| code | int   | 错误码0 则是正常；其他看错误码表  |
| id | string   | 云手机id  |
| ip | string   | 连接ip  |
| port | string   | 端口  |
| pwd | string   | 密码  |


## 错误码

以下为接口特定错误码，其他错误码请参考[云手机错误码](https://open.geelark.cn/api/cloud-phone-error-codes)

| 错误码 | 说明 |
| --- | --- |
| 42001 | 云手机不存在 |
| 42002 | 云手机不处于运行状态 |
| 49001 | adb未开启 |
| 49002 | 机型暂不支持adb |
