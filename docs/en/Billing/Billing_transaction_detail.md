[toc]

API Description
---------------

Query billing transaction detail

Request URL
-----------
- `https://openapi.geelark.com/open/v1/billing/transaction/detail`

Request Method
--------------
- POST

Request Parameters
------------------

| Parameter | Required | Type | Description | Example |
| ----------- | -------| -----------|----------- |--------- |
| id | No | string | Specify the cloud phone ID. If not specified, will be obtained all | "612451567282427943" |
| startAt | No | integer | Filter start time, second-level timestamp (currently only supports searching data within the last 3 days) | 1774593838 |
| endAt | No | integer| Filtering end time, second-level timestamp (currently only supports searching data within the last 3 days)|1774593838|
| limit | No | integer | The acquisition quantity limit is set to 100 by default, with a maximum of 1000 |1 |
| lastFlowId | No | string | The lastFlowId returned from the previous request is used to obtain the data for the next page | "612476158453291064" |

Request Example
---------------

```json
{
	"id": "612451567282427943",
	"limit" : 10,
	"lastFlowId": "612476158453291064",
	"startAt" : 1774593838,
	"endAt": 1774593840
}
```

Response Example
----------------

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

Response Body Description
-------------------------

| Parameter | Type | Description |
| ----------- | -----------|----------- |
| id | string | flow id |
| envId | string | cloud phone id |
| type | integer | Usage type ，1-cloud phone  2-RPA |
| chargeType | integer | Billing type 1-Points 2-Balance 3-Bonus 4-Time add-on 5-Bonus minutes 6-Monthly rental 7-Parallels  8-Daily cap reached|
| amount | float | amount |
| usedTime | integer | Usage duration, minutes|
| createdTime | integer | flow created time, second-level timestamp |
| lastFlowId | string | The last sequential ID, used to retrieve data from the next page |


Response Example
----------------

Error Codes
-----------

Please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes)