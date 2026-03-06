[TOC]

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
| ids | No | array[string] | Environment IDs, maximum is 100. Pagination parameters are used only if left blank | [&quot;5213214343124321&quot;] |
| serialName | No | string | Environment name | myEnv |
| remark | No | string | Remark | myRemark |
| groupName | No | string | Group name | myGroup |
| tags | No | array[string] | Array of tag names | [&quot;myTag&quot;] |


## Request Example


```json
{
 &quot;page&quot;: 1,
 &quot;pageSize&quot;: 10
}
```


## Example response


```json
{
	&quot;traceId&quot;:&quot;Zt0YNAeHR&quot;,
	&quot;code&quot;:0,
	&quot;msg&quot;:&quot;success&quot;,
	&quot;data&quot;:{
		&quot;total&quot;:1,
		&quot;page&quot;:1,
		&quot;pageSize&quot;:10,
		&quot;items&quot;:[
			{
				&quot;id&quot;:&quot;5213214343124321&quot;,
				&quot;serialName&quot;:&quot;myEnv&quot;,
				&quot;serialNo&quot;:&quot;3&quot;,
				&quot;group&quot;:{
					&quot;id&quot;:&quot;5213214343124321&quot;,
					&quot;name&quot;:&quot;myGroup&quot;,
					&quot;remark&quot;:&quot;myRemark&quot;
				},
				&quot;remark&quot;:&quot;myRemark&quot;,
				&quot;tags&quot;:[
					{
						&quot;name&quot;:&quot;myTag&quot;
					}
				],
				&quot;proxy&quot;:{
					&quot;type&quot;:&quot;&quot;,
					&quot;server&quot;:&quot;&quot;,
					&quot;port&quot;:0,
					&quot;username&quot;:&quot;&quot;,
					&quot;password&quot;:&quot;&quot;
				},
				&quot;accountInfo&quot;:{
					&quot;url&quot;:&quot;https://www.tiktok.com/&quot;,
					&quot;userName&quot;:&quot;jay&quot;,
					&quot;passWord&quot;:&quot;password&quot;,
					&quot;afterStartup&quot;:3,
					&quot;autoOpenUrls&quot;:[&quot;http://www.b.com&quot;]
				},
				&quot;simulateInfo&quot;:{
					&quot;os&quot;:2,
					&quot;vendor&quot;:1,
					&quot;mixtureKey&quot;:&quot;87da5186e1feabc1&quot;,
					&quot;ua&quot;:&quot;Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/133.0.6943.141 Safari/537.36&quot;,
					&quot;uaVersion&quot;:&quot;133&quot;,
					&quot;timeZone&quot;:{
						&quot;switcher&quot;:2
					},
					&quot;webRtc&quot;:{
						&quot;switcher&quot;:1
					},
					&quot;geoLocation&quot;:{
						&quot;switcher&quot;:1,
						&quot;baseOnIp&quot;:true,
						&quot;longitude&quot;:20,
						&quot;latitude&quot;:10,
						&quot;accuracy&quot;:1
					},
					&quot;language&quot;:{
						&quot;switcher&quot;:1
					},
					&quot;resolution&quot;:{
						&quot;switcher&quot;:2
					},
					&quot;font&quot;:{
						&quot;switcher&quot;:2
					},
					&quot;canvas&quot;:{
						&quot;switcher&quot;:1
					},
					&quot;webglImage&quot;:{
						&quot;switcher&quot;:1
					},
					&quot;webglMetadata&quot;:{
						&quot;switcher&quot;:3,
						&quot;provider&quot;:&quot;Google Inc. (Intel Inc.)&quot;,
						&quot;render&quot;:&quot;ANGLE (Intel Inc., Intel(R) HD Graphics 6000, OpenGL 4.1)&quot;
					},
					&quot;hardware&quot;:{
						&quot;switcher&quot;:1
					},
					&quot;audioContext&quot;:{
						&quot;switcher&quot;:1
					},
					&quot;mediaDevice&quot;:{
						&quot;switcher&quot;:1
					},
					&quot;clientRects&quot;:{
						&quot;switcher&quot;:1
					},
					&quot;speechVoise&quot;:{
						&quot;switcher&quot;:1
					},
					&quot;hardwareConcurrency&quot;:26,
					&quot;memeryDevice&quot;:8,
					&quot;doNotTrack&quot;:2,
					&quot;bluetooth&quot;:{
						&quot;switcher&quot;:1
					},
					&quot;battery&quot;:{
						&quot;switcher&quot;:1
					},
					&quot;portScanProtection&quot;:{
						&quot;switcher&quot;:1,
						&quot;value&quot;:&quot;80&quot;
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


