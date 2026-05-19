## API Description

API: Batch Import Contacts.

## Request URL

* `https://openapi.geelark.com/open/v1/phone/importContacts`

## Request Method

* POST

## Authentication

All requests are `POST` with `Content-Type: application/json`.

Required headers:

- `traceId`: Version 4 UUID (uppercase recommended)
- **Token mode:** `Authorization: Bearer YOUR_API_TOKEN`
- **Key mode:** `appId`, `traceId`, `ts`, `nonce`, `sign` (see [Request Instructions](../../User%20Guide/Cloud%20Phone/Request_Instructions.md))

## Request Parameters

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| id | Yes | string | Cloud phone ID |
| contacts | Yes | array[ContactObject] | Array of contact information |

### ContactObject
| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| email1 | No | string | Email 1 |
| email2 | No | string | Email 2 |
| fax | No | string | Fax number. At least one of **mobile**, **work**, or **fax** must be non-empty |
| firstName | No | string | First name. At least one of **firstName** or **lastName** must be non-empty |
| lastName | No | string | Last name. At least one of **firstName** or **lastName** must be non-empty |
| mobile | No | string | Mobile phone number. At least one of **mobile**, **work**, or **fax** must be non-empty |
| work | No | string | Work phone number. At least one of **mobile**, **work**, or **fax** must be non-empty |

## Request Example

```json
{
	"id":"557536075321468390",
	"contacts": [
		{
			"firstName": "jay",
			"mobile": "13288888888"
		}
	]
}
```

## Response Example

```json
{
    "traceId": "A4D8BCF69B878A71AC589F5CB1D80EAB",
    "code": 0,
    "msg": "success",
    "data": {
        "taskId": "558017255909123564"
    }
}
```

## Response Body Data Description
|Parameter	|Type|	Description|
| ----------- | -----------|----------- |
|taskId	|string	|Task ID (valid for query one hour after the task is created)|

## Response Data Description

| Field | Type | Description |
| --- | --- | --- |
| traceId | string | Request identifier |
| code | integer | `0` = success |
| msg | string | Status message |
| data | object | Response payload (see example) |

## Error Codes

See [Cloud Phone Error Codes](../../Error%20Codes/Cloud_Phone_Error_Codes.md). Interface-specific codes may also appear in the response `msg` / `code` fields.
