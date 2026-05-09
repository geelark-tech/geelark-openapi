## API Description

Modify cloud phone network settings, including access blacklist

### Access Blacklist

Maximum three blacklisted domains. Settings take effect immediately; the cloud phone will be unable to access domains on the blacklist.

Only supports Android 9/10/11/12/13/15 cloud phones.

## Request URL

- `https://openapi.geelark.com/open/v1/phone/netConfig/set`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type | Description |
| --- | --- | --- | --- |
| blackList | No | array[string] | If a blacklisted domain is accessed, the list will not be updated unless an array is passed; otherwise, the list will be set to null. |


## Request Example
```json
 {
	"blackList": ["c.com"]
}
```

## Response Example

```json
{
    "traceId": "A62BBBF3A294487F9B49B9FFA0F84CA8",
    "code": 0,
    "msg": "success"
}
```