[TOC]

Request URL
-----------

*   `https://openapi.geelark.com/open/v1/phone/importContacts`
    

Request Method
--------------

*   POST
    

Request Parameters
------------------

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

Request Example
---------------
```json
{
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

## Response Body Data Description
|Parameter	|Type|	Description|
| ----------- | -----------|----------- |
|taskId	|string	|Task ID (valid for query one hour after the task is created)|