## API Description

Clears the local cache of the specified browser environment. For data security, please ensure this API is used when the browser environment is not open. If the disk space is insufficient, this API can be used to clear the cache to free up space.

## Request URL

- `http://localhost:40185/api/v1/browser/deleteCache`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type | Example | Description |
| --- | --- | --- | --- | --- |
| ids | Yes | array[string] | ["123456789","987654321"] | Browser ID |
| type | Yes | array[string] | ["local_storage","indexeddb"] | Types of cache to clear. Supported types: local_storage, indexeddb, extension_cache, cookie, history, image_file. |

## Request Example

```json
{
    "ids": [
        "123456789",
        "987654321"
    ],
    "type": [
        "local_storage",
        "indexeddb",
        "extension_cache",
        "cookie",
        "history",
        "image_file"
    ]
}
```

## Response Example

```json
{
    "code": 0,
    "msg": "success",
    "data": {
        "success_count": 2,
        "error_count": 0,
        "error_info": []
    }
}
```

## Error Codes

For error codes, please refer to the [API Call Instructions](https://open.geelark.cn/api/request-instructions)