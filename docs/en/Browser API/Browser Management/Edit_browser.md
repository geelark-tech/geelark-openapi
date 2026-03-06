[TOC]

## Interface Description

Modify environment information, support updating account passwords and cookies, proxy information, fingerprint information, etc.


## Request URL

- `http://localhost:40185/api/v1/browser/update`

## Request method


- POST


## Request Parameters


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | Environment id | 497548067550006541 |
| serialName | No | string | Environment name. If left blank, no change. Maximum 100 characters. | myBrowser |
| groupId | No | string | Environment group id. If omitted, no change. If left blank, the environment is marked as ungrouped. | 497548067550006541 |
| tagIds | No | array[string] | Environment tag ids. If omitted, no change. If left blank, the environment is marked as untagless. | [&quot;497548067550006541&quot;] |
| remark | No | string | Environment remark. Maximum 1500 characters. If left blank, no change. | myRemark |
| cookie | No | string | Cookie. Supports JSON and Netscape formats. | [{&quot;domain&quot;:&quot;.example.com&quot;,&quot;expires&quot;:&quot;2025-12-31T23:59:59Z&quot;,&quot;httpOnly&quot;:true,&quot;name&quot;:&quot;SESSION_ID&quot;,&quot;path&quot;:&quot;/&quot;,&quot;sameSite&quot;:&quot;Lax&quot;,&quot;secure&quot;:true,&quot;value&quot;:&quot;a1b2c3d4e5f67890abcdef1234567890&quot;}] |
| accountPlatform | No | string | Account platform. Will not be changed if not passed. Only supports https://www.tiktok.com/, https://www.facebook.com/ | https://www.tiktok.com/ |
| accountUsername | No | string | Account username. Valid only when accountPlatform is valid. | myUser |
| accountPassword | No | string | Account password. Valid only when accountPlatform is valid. | myPass |
| openTabs | No | string | Opens the specified webpages. Separate multiple pages with &quot;;&quot;. If not passed, no changes will be made. | http://www.b.com |
| browserOs | No | int | Operating system. If not passed, no changes will be made. 1-win, 2-mac | 1 |
| browserUa | No | string | UserAgent. If not passed, no changes will be made. | Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/136.0.7103.93 Safari/537.36 |
| simulateConfig | No | SimulateConfig | Simulate configuration. If not passed, no changes will be made. | See SimulateConfig |
| proxyId | No | string | Proxy ID. Used first. If neither proxyId nor proxyConfig is passed, no changes will be made to the proxy. | 497548067550006541 |
| proxyConfig | No | BrowserApiAddProxy | Proxy information. If neither proxyId nor proxyConfig is passed, the proxy will not be modified. | See BrowserApiAddProxy |
| browserStartArg | No | string | Startup parameters; if not passed, they will not be modified. | -disable-popups |

###  Simulation Configuration SimulateConfig

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| webRtc | yes | object | WebRTC | - |
| webRtc.switcher | yes | int | 1: Privacy, 2: Replace, 3: True, 4: Disable | 1 |
| geoLocation | yes | object | Geolocation | - |
| geoLocation.switcher | yes | int | 1: Ask, 2: Disable, 3: Allow | 1 |
| geoLocation.baseOnIp | yes | bool | Match based on IP | true |
| geoLocation.longitude | yes | int | Latitude | 10 |
| geoLocation.latitude | yes | int | Longitude | 20 |
| geoLocation.accuracy | yes | int | Accuracy (meters) | 10 |
| canvas | yes | object | Canvas | - |
| canvas.switcher | yes | int | 1: Noise, 2: True | 1 |
| webglImage | yes | object | WebGL Image | - |
| webglImage.switcher | Yes | int | 1: Noise, 2: Real | 1 |
| hardware | Yes | object | Hardware Acceleration | - |
| hardware.switcher | Yes | int | 1: Default, 2: Enabled, 3: Disabled | 1 |
| audioContext | Yes | object | AudioContext | - |
| audioContext.switcher | Yes | int | 1: Noise, 2: Disabled | 1 |
| mediaDevice | Yes | object | Media Device | - |
| mediaDevice.switcher | Yes | int | 1: Noise, 2: Disabled | 1 |
| clientRects | Yes | object | ClientRects | - |
| clientRects.switcher | Yes | int | 1: Noise, 2: Disabled | 1 |
| speechVoise | Yes | object | SpeechVoices | - |
| speechVoise.switcher | Yes | int | 1: Noise, 2: Off | 1 |
| hardwareConcurrency | Yes | int | Hardware concurrency | 26 |
| memoryDevice | Yes | int | Device memory | 8 |
| doNotTrack | Yes | int | Do Not Track 0: Default, 1: On, 2: Off | 2 |
| bluetooth | Yes | object | Bluetooth | - |
| bluetooth.switcher | Yes | int | 1: Privacy, 2: True | 1 |
| battery | Yes | object | Battery | - |
| battery.switcher | Yes | int | 1: Privacy, 2: True | 1 |
| portScanProtection | Yes | object | Port scan protection | - |
| portScanProtection.switcher | Yes | int | 1: Enable, 2: Disable | 1 |
| portScanProtection.value | Yes | string | Ports allowed to be scanned, comma separated | 80 |

### Proxy Information BrowserApiAddProxy

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| typeId | yes | int | Proxy type ID. -1 represents a direct connection. | 1 |
| server | no | string | Proxy host | server.com |
| port | no | int | Proxy port | 1234 |
| username | no | string | Proxy username | user |
| password | no | string | Proxy password | password |
| country | no | string | Dynamic proxy country | us |
| region | no | string | Dynamic proxy region | alabama |
| city | no | string | Dynamic proxy city | mobile |
| useProxyCfg | no | bool | Whether to use the configured dynamic proxy. | true |
| protocol | no | int | Dynamic proxy protocol. 1 represents socks5, 2 represents http. | 1 |

### Proxy type id

- `-1` Direct connection
- `1` socks5
- `2` http
- `3` https
- `20` IPIDEA Proxy
- `21` IPHTML Proxy
- `22` kookeey Proxy
- `23` Lumatuo Proxy


## Request Example


```json
{
	&quot;id&quot;:&quot;497548067550006541&quot;,
	&quot;simulateConfig&quot;:{
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
		&quot;canvas&quot;:{
			&quot;switcher&quot;:1
		},
		&quot;webglImage&quot;:{
			&quot;switcher&quot;:1
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
```


## Example response


```json
{
  &quot;traceId&quot;: &quot;123456ABCDEF&quot;,
  &quot;code&quot;: 0,
  &quot;msg&quot;: &quot;success&quot;
}
```


## Error Code


Below are specific error codes for this interface. For other error codes, please refer to [Browser Error Codes](https://open.geelark.com/api/browser-error-codes).


| Error Code | Description |
| --- | --- |
| 45006 | Proxy information error |
| 45003 | Proxy not allowed |
| 45004 | Proxy verification failed |
| 43028 | The sub-user does not have permissions for this environment group |

