## Interface Description

Download or update the specified kernel to the latest version.

> Available in version 4.3.8 and above

## Request URL

- `http://localhost:40185/api/v1/browser/updateKernels`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type | Example | Description
| --- | --- | --- | --- | --- |
| kernel_version | Yes | string | "143" | Browser kernel version |

## Request Example

```json

{
  "kernel_version":"143",
}
```
## Response Example

```json

{
    "code": 0,
    "msg": "success",
    "data": {
        "status": "complete",
        "progress": 0
    }
}
```