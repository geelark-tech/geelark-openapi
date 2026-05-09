## Interface Description

Query and return the current kernel list.

> Available in v4.3.8 and above

## Request URL

- `http://localhost:40185/api/v1/browser/getKernelsList`

## Request Method

- POST

## Response Example

```json

{
    "code": 0,
    "msg": "success",
    "data": [
		{
		"kernel": "147",
        "isDownloaded": true	//Whether it has been downloaded
		}
	]
}
```