[TOC]

## API Description

* The Basic plan supports the creation of only one cloud phone at a time, while the Pro plan supports batch creation.

## Request URL

* `https://openapi.geelark.com/open/v1/phone/add`

## Request Method

* POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| amount | Yes | integer | Total number of cloud phones to create (range: 1-100) | 10 |
| androidVersion | Yes | integer | Cloud phone system version | 1 |
| proxyId | No | string | Proxy ID. You must provide either a Proxy ID or Proxy configuration. Proxy ID takes precedence. | 497548067550006541 |
| proxyConfig | No | object | Proxy configuration | See request example |
| remark | No | string | Remarks, up to 1500 characters | 12ABCDEF |
| groupName | No | string | Group name, created automatically if not existing, up to 50 characters | group1 |
| tagsName | No | array\[string\] | Tag names, created automatically if not existing. The maximum length of a single label is 30 characters | See request example |
| region|No|string|Specify where the cloud phone is located, optional parameters：cn, sgp| cn|
| chargeMode | No | int | charge mode | 0 pay per minute, 1 monthly subscription; default is pay per minute | 
|language|No|string|Language of the cloud phone|baseOnIP/default (default is English)，If this parameter is not provided, it will default to English|
| surfaceBrandName | No | string | Mobile phone brand, obtain the value corresponding to the Android version from the brand list interface, and the brand model should be transmitted at the same time | samsung |
| surfaceModelName | No | string | Mobile phone model, obtain the value corresponding to the Android version from the brand list interface, and the brand model should be transmitted at the same time | Galaxy S23 |
| netType | No | integer | Networking. 0-Wi-Fi, 1-Mobile. Only supported on Android 12/Android 13/Android 15. Default to mobile network | 0 |
| phoneNumber | No | string | Mobile phone number, automatically generated if empty | +66817806147 |

### proxyConfig Static Proxy Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| typeId | Yes | integer | Proxy type ID | 1 |
| server | Yes | string | Proxy server hostname | server.com |
| port | Yes | integer | Proxy server port | 1234 |
| username | Yes | string | Proxy server username | user |
| password | Yes | string | Proxy server password | password |

### proxyConfig Dynamic Proxy Parameters

Dynamic proxy settings can be configured on the client side first, and then by setting useProxyCfg to true, you can use the already configured information without needing to provide the host, port, and other details again.

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| useProxyCfg | Yes | bool | Whether to use the already configured proxy | true |
| typeId | Yes | integer | Proxy type ID | 20 |
| protocol | No | integer | Proxy protocol type: 1 for SOCKS5, 2 for HTTP. | 1 |
| server | No | string | Proxy server hostname | server.com |
| port | No | integer | Proxy server port | 1234 |
| username | No | string | Proxy server username | user |
| password | No | string | Proxy server password | password |
| country | No | string | country | us |
| region | No | string | region | alabama |
| city | No | string | city | mobile |

### androidVersion Corresponding Versions

* `1` : Android 10
* `2` : Android 11
* `3` : Android 12
* `4` : Android 13 
- `5` : Andorid 10 Live Streaming(Only supports monthly subscription charge mode)
- `7` : Andorid 14
* `8` : Android 15

### typeId List
### 1. Static Proxy List

* `1` : socks5
* `2` : http
* `3` : https

### 2. Dynamic Proxy List

- `20` IPIDEA
- `21` IPHTML
- `22` kookeey
- `23` Lumatuo

## Request Example

```json
{
  "amount": 5,
  "androidVersion": 1,
  "proxyConfig":{
    "typeId": 1,
    "server": "server.com",
    "port": 32080,
    "username": "123465ABCD",
    "password": "123465ABCD"
  },
  "groupName": "group",
  "tagsName": [
    "123",
    "ABC"
  ],
  "remark": ""
}

```

## Response Example

```json
{
    "traceId": "123456ABCDEF",
    "code": 0,
    "msg": "success",
    "data": {
        "totalAmount": 1,
        "successAmount": 1,
        "failAmount": 0,
        "details": [
            {
                "index": 1,
                "code": 0,
                "msg": "success",
				"id": "497652752864775437",
                "profileName": "22 ungrouped",
                "envSerialNo": "22",
				"equipmentInfo": {
					"countryName": "Thailand",
					"phoneNumber": "+66877382166",
					"enableSim": 1,
					"imei": "863406055475987",
					"osVersion": "Android 11.0",
					"wifiBssid": "1C:1D:67:B1:C1:76",
					"mac": "9C:A5:C0:5F:C5:AD",
					"bluetoothMac": "D0:15:4A:5B:7E:AE",
					"timeZone": "Asia/Bangkok"
			 	}
            }
        ]
    }
}
```

## Response Data Description

| Parameter Name | Type | Description |
| --- | --- | --- |
| totalAmount | integer | Total number of cloud phones created |
| successAmount | integer | Number of successful creations |
| failAmount | integer | Number of failed creations |
| details | array | Creation response details |

### details Creation Response

| Parameter Name | Type | Description |
| --- | --- | --- |
| index | integer | Creation index |
| code | integer | Result code, 0 for success |
| msg | string | Result message |
| id | string | Cloud phone ID |
| profileName | string | Cloud phone name |
| envSerialNo | string | Cloud phone serial number |
| equipmentInfo  | EquipmentInfo    | cloud phone equipment info |

#### equipmentInfo Cloud phone equipment info <EquipmentInfo>

| Parameter Name | Type | Description |
| ----------- | -----------|----------- |
| countryName | string | country name |
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

## Error Codes

Below are specific error codes for this interface. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 44001 | Batch creation is not allowed, please upgrade to the Pro plan |
| 44002 | Batch creation is not allowed, cloud phone creation limit reached for the plan |
| 44004 | Batch creation is not allowed, maximum daily cloud phone creation limit reached |
| 44006 | phone out of stock|
| 45003 | Proxy banned |
| 45004 | Proxy verification failed |
| 45005 | Region not supported |
| 45001 | The proxy does not exist. |
| 43017 | not enough devices for the monthly plan|
| 43019 | The charge mode of this androidVersion only supports monthly subscription|
| 45008 | Proxy type not allow |
