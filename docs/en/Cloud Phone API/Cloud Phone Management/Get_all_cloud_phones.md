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
| ids | No | array[string] | Cloud phone ID array，The maximum length of the array is 100. If the array is not empty, these two parameters： page pageSize, will not take effect | [&quot;5213214343124321&quot;] |
| serialName | No | string | Cloud phone name | test |
| remark | No | string | Cloud phone remark | test |
| groupName | No | string | Cloud phone group name | test group |
| tags | No | array\[string\] | List of cloud phone tag names | See example |
| chargeMode | No | int | charge mode | 0 pay per minute, 1 monthly subscription; If this field is left empty, all charge mode will be queried. | 
| openStatus        |  no     |   integer  | Power state  | 0 Close；1 On |
| proxyIds        |  no     |  array[string]   | List of proxy IDs. The maximum array length is 10. |  [&quot;5213214343124321&quot;]  |
| serialNos        |  no     |  array[string]   | List of cloud phone serial number. The maximum array length is 100. |  [&quot;238&quot;]  |

## Request Example
``` json
{
    &quot;page&quot;:1,
    &quot;pageSize&quot;:10,
    &quot;serialName&quot;: &quot;test&quot;,
    &quot;remark&quot;:&quot;&quot;,
    &quot;groupName&quot;:&quot;&quot;,
	&quot;tags&quot;:[
		&quot;tag1&quot;,
		&quot;tag2&quot;
	],
	&quot;openStatus&quot; : 1,
	&quot;proxyIds&quot;: [&quot;602943680722009770&quot;],
	&quot;serialNos&quot;: [&quot;238&quot;]
}
```

### Response Data Description

| Parameter Name | Type | Description |
| --- | --- | --- |
| total | integer | Total number of cloud phones |
| page | integer | Page number |
| pageSize | integer | Page size |
| items | array\[Phone\] | List of cloud phones |

### items Cloud Phone Data &lt;Phone&gt;

| Parameter Name | Type | Description |
| --- | --- | --- |
| id | string | Cloud phone ID |
| serialName | string | Cloud phone name |
| serialNo | string | Cloud phone serial number |
| group | Group | Cloud phone group information |
| remark | string | Cloud phone remark |
| status | int | Cloud phone status&lt;br/&gt;0 - Started&lt;br/&gt;1 - Starting&lt;br/&gt;2 - Shut down |
| tags | array\[Tag\] | List of cloud phone tags |
| equipmentInfo  | EquipmentInfo    | cloud phone equipment info |
| proxy | Proxy | Proxy info |
| chargeMode | int | charge mode: 0 pay per minute, 1 monthly subscription| 
| hasBind | bool | Is the device bound to a monthly subscription |
| monthlyExpire | int | Monthly subscription expiration time, timestamp in seconds |
| rpaStatus | int | Whether RPA is running: 1 = running, 0 = not running |

### group Group Information &lt;Group&gt;

| Parameter Name | Type | Description |
| --- | --- | --- |
| id | string | Group ID |
| name | string | Group name |
| remark | string | Group remark |

### tags Cloud Phone Tags &lt;Tag&gt;

| Parameter Name | Type | Description |
| --- | --- | --- |
| name | string | Cloud phone tag name |

### equipmentInfo Cloud phone equipment info &lt;EquipmentInfo&gt;

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

### proxy Proxy info &lt;Proxy&gt;

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
    &quot;traceId&quot;: &quot;123456ABCDEF&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;total&quot;: 1,
        &quot;page&quot;: 1,
        &quot;pageSize&quot;: 10,
        &quot;items&quot;: [
            {
                &quot;id&quot;: &quot;123456ABCDEF&quot;,
                &quot;serialName&quot;: &quot;test&quot;,
                &quot;serialNo&quot;: &quot;1&quot;,
                &quot;group&quot;: {
                    &quot;id&quot;: &quot;123456ABCDEF&quot;,
                    &quot;name&quot;: &quot;test group&quot;,
                    &quot;remark&quot;: &quot;group remark&quot;
                },
                &quot;remark&quot;: &quot;env remark&quot;,
				&quot;status&quot;: 0,
                &quot;tags&quot;: [
					{&quot;name&quot;: &quot;hi&quot;},
					{&quot;name&quot;: &quot;test&quot;}
				],
				&quot;equipmentInfo&quot;: {
					&quot;countryName&quot;: &quot;Thailand&quot;,
					&quot;phoneNumber&quot;: &quot;+66877382166&quot;,
					&quot;enableSim&quot;: 1,
					&quot;imei&quot;: &quot;863406055475987&quot;,
					&quot;osVersion&quot;: &quot;Android 11.0&quot;,
					&quot;wifiBssid&quot;: &quot;1C:1D:67:B1:C1:76&quot;,
					&quot;mac&quot;: &quot;9C:A5:C0:5F:C5:AD&quot;,
					&quot;bluetoothMac&quot;: &quot;D0:15:4A:5B:7E:AE&quot;,
					&quot;timeZone&quot;: &quot;Asia/Bangkok&quot;,
					&quot;deviceName&quot;: &quot;&quot;,
                    &quot;netType&quot;: 1,
                    &quot;language&quot;: &quot;en-US&quot;,
                    &quot;province&quot;: &quot;&quot;,
                    &quot;city&quot;: &quot;&quot;
				 },
				&quot;proxy&quot;: {
					&quot;type&quot;: &quot;socks5&quot;,
					&quot;server&quot;: &quot;129.129.129.129&quot;,
					&quot;port&quot;: 30000,
					&quot;username&quot;: &quot;user&quot;,
					&quot;password&quot;: &quot;pass&quot;
				}
            }
        ]
    }
}
```

## Error Codes

Error codes can be found in the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).
