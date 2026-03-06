## API Description
Get a screen shot from cloud phone

## Request URL

- `https://openapi.geelark.com/open/v1/phone/screenShot`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | clound phone id | Refer to request example  |


## Request Example
```json
{
    "id": "528715748189668352"
}
```



## Response Example

```json
{
    "traceId": "A62BBBF3A294487F9B49B9FFA0F84CA8",
    "code": 0,
    "msg": "success",
	"data": {
        "taskId": "1850726441252569088"
    }
}
```

## Response Data Description

| Parameter Name | Type | Description |
| ----------- | -----------|----------- |
| taskId | string | task id |


## Error Codes


The following are specific error codes for this API. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes)


| Error Code | Description |
| --- | --- |
| 42001 | Cloud phone does not exist |
| 42002 | Cloud phone is not running |


Callback Result and Example
---------------------------

Please refer to Callback Example
