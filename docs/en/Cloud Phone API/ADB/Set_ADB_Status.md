## API Description

API: Set ADB Status.

## Request URL

* `https://openapi.geelark.com/open/v1/adb/setStatus`

## Request Method

* POST

## Authentication

All requests are `POST` with `Content-Type: application/json`.

Required headers:

- `traceId`: Version 4 UUID (uppercase recommended)
- **Token mode:** `Authorization: Bearer YOUR_API_TOKEN`
- **Key mode:** `appId`, `traceId`, `ts`, `nonce`, `sign` (see [Request Instructions](../../User%20Guide/Cloud%20Phone/Request_Instructions.md))

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| ids | Yes | array\[string\] | Array of cloud phone environment IDs, maximum 200| Refer to request example |
| open | Yes | bool | Open/Close | false |

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
 "msg": "success"
}
```

## Request Example

_See parameter table._

## Response Example

_Standard envelope; see Response Data Description._

## Response Data Description

| Field | Type | Description |
| --- | --- | --- |
| traceId | string | Request identifier |
| code | integer | `0` = success |
| msg | string | Status message |
| data | object | Response payload (see example) |

## Error Codes

See [Cloud Phone Error Codes](../../Error%20Codes/Cloud_Phone_Error_Codes.md). Interface-specific codes may also appear in the response `msg` / `code` fields.
