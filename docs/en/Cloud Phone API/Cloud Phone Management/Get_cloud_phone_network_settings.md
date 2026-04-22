## API Description

Obtain cloud phone network settings, including access to blacklists.

## Request URL

- `https://openapi.geelark.com/open/v1/phone/netConfig/get`

## Request Method

- POST

## Response Data Description

| Parameter Name | Type | Description |
| ----------- | -----------|----------- |
| blackList |  array[string] | Accessing blacklisted domains |

## Response Example

```json
{
    "traceId": "B3DAFF64A7BD493CB1169D94A22BFC8D",
    "code": 0,
    "msg": "success",
	"data": {
		"blackList": ["c.com"]
	}
}
```