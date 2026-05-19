## 接口说明

- 目前ADB支持Android 9、11、12、13、14、15、16机型
- 设置ADB状态，在打开ADB前，请先启动云手机
- ADB打开为异步操作，建议打开ADB后，等待3秒左右再获取端口密码等信息

## 请求URL

- `https://openapi.geelark.cn/open/v1/adb/setStatus`

## 请求方法

- POST


## 鉴权

所有请求均为 `POST`，请求头需设置 `Content-Type: application/json`。

必需请求头：

- `traceId`：Version 4 UUID（建议大写）
- **Token 模式：** `Authorization: Bearer YOUR_API_TOKEN`
- **Key 模式：** `appId`、`traceId`、`ts`、`nonce`、`sign`（见 [接口调用说明](../../使用指南/云手机/接口调用说明.md)）

## 请求参数

| 参数名 | 必选 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- | --- |
| ids | 是 |array[string] | 云手机环境id数组，最多200个 | 526209711930868736 |
| open | 是 | bool | 打开/关闭 | false |

## 请求示例

```json
{
 	"ids" : [
		 "526209711930868736"
	 ],
 	"open" : true
}
```


## 响应示例

```json
{
 "traceId": "A24A3089958A4BC28E8B89B3AE1A61AC",
 "code": 0,
 "msg": "success"
}
```

## 错误码

错误码请参考[云手机错误码](../../错误码/云手机错误码.md)