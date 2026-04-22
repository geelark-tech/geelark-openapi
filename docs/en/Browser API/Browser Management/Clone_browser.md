## API Description

- Generate a brand new browser with the same operating system and advanced settings

## Request URL

- `http://localhost:40185/api/v1/browser/clone`


## Request Method
- POST

## Request Parameters

| Parameter Name | Required | Type | Description |
| --- | --- | --- | --- |
|envId|Yes|string|Browser ID to clone|
|amount|Yes|int|Number of clones, range 1-100|
|groupId|No|string|Target group ID, if not specified, it will be placed in an ungrouped group|
|cloneName|No|bool|Whether to clone the name|
|cloneRemark|No|bool|Whether to clone the remark|
|cloneTag|No|bool|Whether to clone the tag|
|cloneProxy|No|bool|Whether to clone the proxy|
|cloneCookie|No|bool|Whether to clone the cookie|
|cloneAccount|No|bool|Whether to clone the account information|

## Request Example
```json
{
    "envId": "590711571886417452",
	"amount": 1,
    "groupId": "590711571886417453"
}
```

## Response Data Description

| Parameter Name | Type | Description |
| ----------- | -----------|----------- |
| ids | array[string] |cloned browser ID|


## Response Example

```json
{
    "traceId": "B3DAFF64A7BD493CB1169D94A22BFC8D",
    "code": 0,
    "msg": "success",
    "data": {
        "ids": [
            "590711571886417454"
        ]
    }
}
```