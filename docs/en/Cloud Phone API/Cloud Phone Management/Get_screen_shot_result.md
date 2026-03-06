## API Description
Query the status of cloud phone screenshot task
After requesting a screenshot, you can actively obtain the result through this interface within 30 minutes. If it expires, the retrieval will fail

## Request URL

- `https://openapi.geelark.com/open/v1/phone/screenShot/result`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| taskId | Yes | string | task id | Refer to request example |


## Request Example
```json
{
    "taskId": "528715748189668352"
}
```



## Response Example

```json
{
    "traceId": "A62BBBF3A294487F9B49B9FFA0F84CA8",
    "code": 0,
    "msg": "success",
	"data": {
        "status": 2,
		"downloadLink": "https://zx-cloud-phone-pre.obs.cn-southwest-2.myhuaweicloud.com/envirFileExport/1851511129017700352/IMG_20241122160248.png?AccessKeyId=UFNIPAPFJX2MAGMFGRYZ&amp;Expires=1732264377&amp;Signature=dqV5JYzYDdm0wwAgkZIpDrs%2FL%2FE%3D"
    }
}
```

## Response Data Description

| Parameter Name | Type | Description |
| ----------- | -----------|----------- |
| status | int | 0 Acquisition failed；1 In progress；2 Execution succeeded；3 Execution failed |
| downloadLink | downloadLink | screen shot download link |


## 错误码

For error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).


