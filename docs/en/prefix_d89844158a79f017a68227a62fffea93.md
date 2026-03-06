[TOC]

## API Description

Retrieve the list of cloud phones.

## Request URL

* `https://openapi.geelark.com/open/v1/phone/list`

## Request Method

* POST

## Request Parameters

### Pagination Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| page | No | integer | Page number, minimum is 1 | 1 |
| pageSize | No | integer | Number of records per page, minimum is 1, maximum is 100 | 10 |

### Query Parameters (Ignored if empty)

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| ids | No | array[string] | Cloud phone ID array，The maximum length of the array is 100. If the array is not empty, these two parameters： page pageSize, will not take effect | ["5213214343124321"] |
| serialName | No | string | Cloud phone name | test |
| remark | No | string | Cloud phone remark | test |
| groupName | No | string | Cloud phone group name | test group |
| tags | No | array\[string\] | List of cloud phone tag names | See example |
| chargeMode | No | int | charge mode | 0 pay per minute, 1 monthly subscription; If this field is left empty, all charge mode will be queried. | 
| openStatus        |  no     |   integer  | Power state  | 0 Close；1 On |
| proxyIds        |  no     |  array[string]   | List of proxy IDs. The maximum array length is 10. |  ["5213214343124321"]  |
| serialNos        |  no     |  array[string]   | List of cloud phone serial number. The maximum array length is 100. |  ["238"]  |

## Request Example
``` json
{
    "page":1,
    "pageSize":10,
    "serialName": "test",
    "remark":"",
    "groupName":"",
	"tags":[
		"tag1",
		"tag2"
	],
	"openStatus" : 1,
	"proxyIds": ["602943680722009770"],
	"serialNos": ["238"]
}
```

### Response Data Description

| Parameter Name | Type | Description |
| --- | --- | --- |
| total | integer | Total number of cloud phones |
| page | integer | Page number |
| pageSize | integer | Page size |
| items | array\[Phone\] | List of cloud phones |

### items Cloud Phone Data <Phone>

| Parameter Name | Type | Description |
| --- | --- | --- |
| id | string | Cloud phone ID |
| serialName | string | Cloud phone name |
| serialNo | string | Cloud phone serial number |
| group | Group | Cloud phone group information |
| remark | string | Cloud phone remark |
| status | int | Cloud phone status<br/>0 - Started<br/>1 - Starting<br/>2 - Shut down |
| tags | array\[Tag\] | List of cloud phone tags |
| equipmentInfo  | EquipmentInfo    | cloud phone equipment info |
| proxy | Proxy | Proxy info |
| chargeMode | int | charge mode: 0 pay per minute, 1 monthly subscription| 
| hasBind | bool | Is the device bound to a monthly subscription |
| monthlyExpire | int | Monthly subscription expiration time, timestamp in seconds |
| rpaStatus | int | Whether RPA is running: 1 = running, 0 = not running |

### group Group Information <Group>

| Parameter Name | Type | Description |
| --- | --- | --- |
| id | string | Group ID |
| name | string | Group name |
| remark | string | Group remark |

### tags Cloud Phone Tags <Tag>

| Parameter Name | Type | Description |
| --- | --- | --- |
| name | string | Cloud phone tag name |

### equipmentInfo Cloud phone equipment info <EquipmentInfo>

| Parameter Name | Type | Description |
| ----------- | -----------|----------- |
| countryName | string | country name, please refer to the [Country Name Reference Table](https://material.geelark.com/t_region.xls) |
| phoneNumber | string | phone number |
| enableSim | int | is Sim enable : 0 unable 1 enable |
| imei | string | IMEI |
| osVersion | string | system version |
| wifiBssid | string | Wi-Fi MAC Address |
| mac | string | phone Wi-Fi MAC Address |
| bluetoothMac | string | bluetooth Mac Address |
| timeZone | string | timezone |
|deviceBrand|string|brand|
|deviceModel|string|model|
|deviceName|string|Device name| 
|netType|integer|Network type: 0 – Wi-Fi, 1 – Mobile network| 
|language|string|Cloud phone language| 
|province|string|Province; only populated if specified at creation time| 
|city|string|City; only populated if specified at creation time|

### proxy Proxy info <Proxy>

| Parameter Name | Type | Description |
| ----------- | -----------|----------- |
| type | string | Proxy type (socks5, http, https) |
| server | string | Proxy server |
| port | int | Proxy port|
| username | string | Proxy username |
| password | string | Proxy password |

## Response Example
```json
{
    "traceId": "123456ABCDEF",
    "code": 0,
    "msg": "success",
    "data": {
        "total": 1,
        "page": 1,
        "pageSize": 10,
        "items": [
            {
                "id": "123456ABCDEF",
                "serialName": "test",
                "serialNo": "1",
                "group": {
                    "id": "123456ABCDEF",
                    "name": "test group",
                    "remark": "group remark"
                },
                "remark": "env remark",
				"status": 0,
                "tags": [
					{"name": "hi"},
					{"name": "test"}
				],
				"equipmentInfo": {
					"countryName": "Thailand",
					"phoneNumber": "+66877382166",
					"enableSim": 1,
					"imei": "863406055475987",
					"osVersion": "Android 11.0",
					"wifiBssid": "1C:1D:67:B1:C1:76",
					"mac": "9C:A5:C0:5F:C5:AD",
					"bluetoothMac": "D0:15:4A:5B:7E:AE",
					"timeZone": "Asia/Bangkok",
					"deviceName": "",
                    "netType": 1,
                    "language": "en-US",
                    "province": "",
                    "city": ""
				 },
				"proxy": {
					"type": "socks5",
					"server": "129.129.129.129",
					"port": 30000,
					"username": "user",
					"password": "pass"
				}
            }
        ]
    }
}
```

## Error Codes

Error codes can be found in the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).
