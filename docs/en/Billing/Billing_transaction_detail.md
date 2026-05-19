## API Description

API: Billing transaction detail.

## Request URL

* `https://openapi.geelark.com/open/v1/billing/transaction/detail`

## Request Method

* POST

## Authentication

All requests are `POST` with `Content-Type: application/json`.

Required headers:

- `traceId`: Version 4 UUID (uppercase recommended)
- **Token mode:** `Authorization: Bearer YOUR_API_TOKEN`
- **Key mode:** `appId`, `traceId`, `ts`, `nonce`, `sign` (see [Request Instructions](../User%20Guide/Cloud%20Phone/Request_Instructions.md))

## Request Parameters

| Parameter | Required | Type | Description | Example |
| ----------- | -------| -----------|----------- |--------- |
| id | No | string | Specify the cloud phone ID. If not specified, will be obtained all | "612451567282427943" |
| startAt | No | integer | Filter start time, second-level timestamp (currently only supports searching data within the last 3 days) | 1774593838 |
| endAt | No | integer| Filtering end time, second-level timestamp (currently only supports searching data within the last 3 days)|1774593838|
| limit | No | integer | The acquisition quantity limit is set to 100 by default, with a maximum of 1000 |1 |
| lastFlowId | No | string | The lastFlowId returned from the previous request is used to obtain the data for the next page | "612476158453291064" |

## Request Example

```json
{
	"id": "612451567282427943",
	"limit" : 10,
	"lastFlowId": "612476158453291064",
	"startAt" : 1774593838,
	"endAt": 1774593840
}
```

## Response Example

```json
{
	"traceId": "9DBBF7A080B099189E2D84CF92287189",
	"code": 0,
	"msg": "success",
	 "data": {
		"total": 1,
		"page": 1,
		"pageSize": 10,
		"list": [
			{
				"id": "612451567282427943",
				"envId": "612451567282427942",
				"amount": 0,
				"usedTime": 2,
				"type": 1,
				"chargeType": 5,
				"createdTime": 1774593838
			}
		],
		"lastFlowId" : "612451567282427943"
	}
}
```

## Response Data Description

| Field | Type | Description |
| --- | --- | --- |
| traceId | string | Request identifier |
| code | integer | `0` = success |
| msg | string | Status message |
| data | object | Response payload (see example) |

## Error Codes

See [Cloud Phone Error Codes](../Error%20Codes/Cloud_Phone_Error_Codes.md). Interface-specific codes may also appear in the response `msg` / `code` fields.
