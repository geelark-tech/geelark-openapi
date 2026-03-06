[TOC]

## Interface Description
Execute shell commands on cloud phones.

- Only supports `Android10`/ `Android12`/`Andriod13`/`Andriod14`/`Andriod15` models.

## Request URL

- `https://openapi.geelark.com/open/v1/shell/execute`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| -------------- | -------- | ------ | --------------------- | ----------------- |
| id | Yes | string | Cloud phone ID | Refer to Request Example |
| cmd | Yes | string | Command to execute | Refer to Request Example |

## Request Example
```json
{
 &quot;id&quot;: &quot;528715748189668352&quot;,
 &quot;cmd&quot;: &quot;pm list packages&quot;
}
```

## Response Example

```json
{
 &quot;traceId&quot;: &quot;924A8E4AAC9E0B0B96ABA7B8801B2CBE&quot;,
 &quot;code&quot;: 0,
 &quot;msg&quot;: &quot;success&quot;,
 &quot;data&quot;: {
 &quot;status&quot;: true,
		&quot;output&quot;: &quot;com.zhiliaoapp.musically&quot;
 }
}
```

## Response Data Description

| Parameter Name | Type | Description |
| -------------- | ------ | ------------------------------------ |
| status | bool | true: Execution successful, false: Execution failed |
| output | string | Execution result |

## Error Codes

Below are the specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| ---------- | ---------------------------------- |
| 42001 | Cloud phone does not exist |
| 42002 | Cloud phone is not in running state |
| 50001 | Cloud phone does not support shell commands |