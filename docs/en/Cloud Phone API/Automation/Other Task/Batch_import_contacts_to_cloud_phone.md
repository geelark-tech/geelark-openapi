
Request URL
-----------

* `https://openapi.geelark.com/open/v1/rpa/task/importContacts`

Request Method
--------------

* POST

Request Parameters
------------------

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| name | No | string | Task name, up to 128 characters |
| remark | No | string | Remarks, up to 200 characters |
| scheduleAt | Yes | int | Scheduled time (timestamp) |
| id | Yes | string | Cloud phone ID |
| contacts | Yes | array[ContactParam] | Array of contact information |

### Contact Information - ContactParam

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
|email1|No|string|Email 1|
|email2|No|string|Email 2|
|fax|No|string|Fax number. At least one of the mobile phone number, work mobile phone number and fax number must be non-empty|
|firstName|No|string|First name. At least one of the first name and last name must be non-empty|
|lastName|No|string|Last name. At least one of the first name and last name must be non-empty|
|mobile|No|string|Mobile phone number. At least one of the mobile phone number, work mobile phone number and fax number must be non-empty|
|work|No|string|Work mobile phone number. At least one of the mobile phone number, work mobile phone number and fax number must be non-empty|

Request Example
----------------

```json
{
	"name":"test",
	"remark":"test remark",
	"scheduleAt": 1741846843,
	"id":"557536075321468390",
	"contacts": [
		{
			"firstName": "jay",
			"mobile": "13288888888"
		}
	]
}
```

Response Example
----------------

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