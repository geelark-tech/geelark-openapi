[TOC]


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
	&quot;name&quot;:&quot;test&quot;,
	&quot;remark&quot;:&quot;test remark&quot;,
	&quot;scheduleAt&quot;: 1741846843,
	&quot;id&quot;:&quot;557536075321468390&quot;,
	&quot;contacts&quot;: [
		{
			&quot;firstName&quot;: &quot;jay&quot;,
			&quot;mobile&quot;: &quot;13288888888&quot;
		}
	]
}
```

Response Example
----------------

```json
{
    &quot;traceId&quot;: &quot;A4D8BCF69B878A71AC589F5CB1D80EAB&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;taskId&quot;: &quot;558017255909123564&quot;
    }
}
```