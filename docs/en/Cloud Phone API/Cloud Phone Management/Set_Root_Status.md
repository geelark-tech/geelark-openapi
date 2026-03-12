## API Description
Set root status, please start the cloud phone before setting root status.

## Request URL

- `https://openapi.geelark.com/open/v1/root/setStatus`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| ids | Yes |array[string] | List of cloud phone IDs ( currently supports Android 12,13,14,15 ) | Refer to request example |
| open | Yes | bool | open/close | false |


## Request Example
```json
{
    "ids" : [
        "526209711930868736"
    ],
    "open" : true
}
```



## Response Example

```json
{
    "traceId": "A24A3089958A4BC28E8B89B3AE1A61AC",
    "code": 0,
    "msg": "success",
	"data": {
        "items": [
            {
                "code": 42002,
                "msg": "phone is not running",
                "id": "543483007558772199"
            },
            {
                "code": 0,
                "msg": "success",
                "id": "543483063829554663"
            }
        ]
    }
}
```


## Error Codes

For error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 42001 | cloud phone not found |
| 42002 | cloud phone is not running |
| 43016 | this cloud phone does not support root |