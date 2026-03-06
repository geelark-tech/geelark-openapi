## 接口说明

- 目前ADB支持Android 9、11、12、13、14、15机型
- 设置ADB状态，在打开ADB前，请先启动云手机
- ADB打开为异步操作，建议打开ADB后，等待3秒左右再获取端口密码等信息

## 请求URL

- `https://openapi.geelark.cn/open/v1/adb/setStatus`

## 请求方法

- POST

## 请求参数

| 参数名 | 必选 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- | --- |
| ids | 是 |array[string] | 云手机环境id数组（目前仅支持安卓11、12、13、14、15类型的机器，不支持的机型会自动过滤） | 526209711930868736 |
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

错误码请参考[云手机错误码](https://open.geelark.cn/api/cloud-phone-error-codes)

