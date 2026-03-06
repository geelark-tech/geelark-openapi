## Interface Description

Query the created environment information, including agent information, agent ID, etc.


## Request URL

- `http://localhost:40185/api/v1/browser/list`

## Request method


- POST


## Request Parameters


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| page | No | int | Page number, minimum is 1, defaults to 1 if left blank | 1 |
| pageSize | No | int | Number of records per page, minimum is 1, maximum is 100, defaults to 10 if left blank | 10 |
| ids | No | array[string] | Environment IDs, maximum is 100. Pagination parameters are used only if left blank | ["5213214343124321"] |
| serialName | No | string | Environment name | myEnv |
| remark | No | string | Remark | myRemark |
| groupName | No | string | Group name | myGroup |
| tags | No | array[string] | Array of tag names | ["myTag"] |


## Request Example


```json
{
 "page": 1,
 "pageSize": 10
}
```


## Example response


```json
{
	"traceId":"Zt0YNAeHR",
	"code":0,
	"msg":"success",
	"data":{
		"total":1,
		"page":1,
		"pageSize":10,
		"items":[
			{
				"id":"5213214343124321",
				"serialName":"myEnv",
				"serialNo":"3",
				"group":{
					"id":"5213214343124321",
					"name":"myGroup",
					"remark":"myRemark"
				},
				"remark":"myRemark",
				"tags":[
					{
						"name":"myTag"
					}
				],
				"proxy":{
					"type":"",
					"server":"",
					"port":0,
					"username":"",
					"password":""
				},
				"accountInfo":{
					"url":"https://www.tiktok.com/",
					"userName":"jay",
					"passWord":"password",
					"afterStartup":3,
					"autoOpenUrls":["http://www.b.com"]
				},
				"simulateInfo":{
					"os":2,
					"vendor":1,
					"mixtureKey":"87da5186e1feabc1",
					"ua":"Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/133.0.6943.141 Safari/537.36",
					"uaVersion":"133",
					"timeZone":{
						"switcher":2
					},
					"webRtc":{
						"switcher":1
					},
					"geoLocation":{
						"switcher":1,
						"baseOnIp":true,
						"longitude":20,
						"latitude":10,
						"accuracy":1
					},
					"language":{
						"switcher":1
					},
					"resolution":{
						"switcher":2
					},
					"font":{
						"switcher":2
					},
					"canvas":{
						"switcher":1
					},
					"webglImage":{
						"switcher":1
					},
					"webglMetadata":{
						"switcher":3,
						"provider":"Google Inc. (Intel Inc.)",
						"render":"ANGLE (Intel Inc., Intel(R) HD Graphics 6000, OpenGL 4.1)"
					},
					"hardware":{
						"switcher":1
					},
					"audioContext":{
						"switcher":1
					},
					"mediaDevice":{
						"switcher":1
					},
					"clientRects":{
						"switcher":1
					},
					"speechVoise":{
						"switcher":1
					},
					"hardwareConcurrency":26,
					"memeryDevice":8,
					"doNotTrack":2,
					"bluetooth":{
						"switcher":1
					},
					"battery":{
						"switcher":1
					},
					"portScanProtection":{
						"switcher":1,
						"value":"80"
					}
				}
			}
		]
	}
}
```


## Response body data description


| Parameter Name | Type | Description |
| --- | --- | --- |
| total | int | Total number of data |
| page | int | Current page number |
| pageSize | int | Number of data items per page |
| items | array[BrowserApiSearchSimpleItem] | Data list |

### Browser data BrowserApiSearchSimpleItem

| Parameter Name | Type | Description |
| --- | --- | --- |
| id | string | Environment id |
| serialName | string | Environment name |
| serialNo | string | Environment number |
| group | EnvGroup | Environment group |
| remark | string | Remark |
| tags | array[EnvTag] | Environment tags |
| proxy | EnvPhoneListProxy | Proxy information |
| accountInfo | BrowserApiSearchSimpleAccount | Account information |
| simulateInfo | BrowserApiSearchSimpleSimulate | Simulation information |

### Environmental Grouping EnvGroup

| Parameter Name | Type | Description |
| --- | --- | --- |
| id | string | Environment group id |
| name | string | Environment group name |
| remark | string | Environment group remark |

### Environmental Label EnvTag

| Parameter Name | Type | Description |
| --- | --- | --- |
| name | string | Tag Name |

### Proxy Information EnvPhoneListProxy

| Parameter Name | Type | Description |
| --- | --- | --- |
| type | string | Proxy type |
| server | string | Proxy host |
| port | int | Proxy port |
| username | string | Proxy username |
| password | string | Proxy password |

### Account Information BrowserApiSearchSimpleAccount

| Parameter Name | Type | Description |
| --- | --- | --- |
| url | string | Platform address |
| userName | string | Platform account |
| passWord | string | Platform password |
| afterStartup | int | Page to open after startup. 1 - Restore last access, 2 - Open the specified URL, 3 - Open the specified URL and the platform page simultaneously, 4 - Restore last access and the platform page simultaneously |
| autoOpenUrls | array[string] | Specified URL |

### Simulation Information BrowserApiSearchSimpleSimulate

| Parameter Name | Type | Description |
| --- | --- | --- |
| os | int | Operating system, 1: Win, 2: Mac |
| vendor | int | Browser type, 1: Chrome |
| mixtureKey | string | Fingerprint algorithm ID |
| ua | string | User agent |
| uaVersion | string | Browser version, 0 represents all |
| timeZone | object | Time zone |
| timeZone.switcher | int | 1: Match based on IP address, 2: Custom |
| webRtc | object | WebRTC |
| webRtc.switcher | int | 1: Privacy, 2: Replace, 3: Real, 4: Disable |
| geoLocation | object | Geolocation |
| geoLocation.switcher | int | 1: Ask, 2: Disable, 3: Allow |
| geoLocation.baseOnIp | bool | Match based on IP address |
| geoLocation.longitude | int | Latitude |
| geoLocation.latitude | int | Longitude |
| geoLocation.accuracy | int | Accuracy (meters) |
| language | object | Language |
| language.switcher | int | 1: IP-based matching, 2: Custom |
| resolution | object | Resolution |
| resolution.switcher | int | 1: Random, 2: Custom |
| font | object | Font |
| font.switcher | int | 1: Default, 2: Custom |
| canvas | object | Canvas |
| canvas.switcher | int | 1: Noise, 2: Real |
| webglImage | object | WebGL Image |
| webglImage.switcher | int | 1: Noise, 2: Real |
| webglMetadata | object | WebGL Metadata |
| webglMetadata.switcher | int | 2: Disabled, 3: Custom |
| webglMetadata.provider | string | WebGL Provider |
| webglMetadata.render | string | WebGL Rendering |
| hardware | object | Hardware acceleration |
| hardware.switcher | int | 1: Default, 2: Enabled, 3: Disabled |
| audioContext | object | AudioContext |
| audioContext.switcher | int | 1: Noise, 2: Disabled |
| mediaDevice | object | Media device |
| mediaDevice.switcher | int | 1: Noise, 2: Disabled |
| clientRects | object | ClientRects |
| clientRects.switcher | int | 1: Noise, 2: Disabled |
| speechVoise | object | SpeechVoices |
| speechVoise.switcher | int | 1: Noise, 2: Disabled |
| hardwareConcurrency | int | Hardware concurrency |
| memoryDevice | int | Device memory |
| doNotTrack | int | Do Not Track 0: Default, 1: Enabled, 2: Disabled |
| bluetooth | object | Bluetooth |
| bluetooth.switcher | int | 1: Private, 2: True |
| battery | object | Battery |
| battery.switcher | int | 1: Private, 2: True |
| portScanProtection | object | Port scan protection |
| portScanProtection.switcher | int | 1: Enable, 2: Disable |
| portScanProtection.value | string | Comma-separated list of ports allowed to be scanned |


## Error Code


Please refer to [Browser Error Codes](https://open.geelark.com/api/browser-error-codes).


