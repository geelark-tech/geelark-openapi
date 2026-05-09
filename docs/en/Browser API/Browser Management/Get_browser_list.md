## Interface Description


Query the created environment information, including agent information, agent ID, etc.



## Request URL


- `http://localhost:40185/api/v1/browser/list`


## Request method



- POST



## Request Parameters



| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| page | No | integer | Page number, minimum is 1, defaults to 1 if left blank | 1 |
| pageSize | No | integer | Number of records per page, minimum is 1, maximum is 100, defaults to 10 if left blank | 10 |
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
                    "totpSecret": "",
                    "afterStartup":3,
                    "openLastPage": 2,
                    "openSpecPage": 1,
                    "openSiteUrl": true,
                    "autoOpenUrls":["http://www.b.com"]
                },
                "simulateInfo":{
                    "os":2,
                    "vendor":1,
                    "mixtureKey":"87da5186e1feabc1",
                    "ua":"Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/133.0.6943.141 Safari/537.36",
                    "uaVersion":"133",
                    "timeZone":{
                        "switcher":2,
                        "value": "GMT-12:00 Etc/GMT+12"
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
                        "switcher":2,
                        "value": "Albanian"
                    },
                    "resolution":{
                        "switcher":2,
                        "value": "750*1334"
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
| total | integer | Total number of data |
| page | integer | Current page number |
| pageSize | integer | Number of data items per page |
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
| port | integer | Proxy port |
| username | string | Proxy username |
| password | string | Proxy password |


### Account Information BrowserApiSearchSimpleAccount


| Parameter Name | Type | Description |
| --- | --- | --- |
| url | string | Platform address |
| userName | string | Platform account |
| passWord | string | Platform password |
| totpSecret | string | 2FA key |
| afterStartup | integer | Page to open after startup. 1 - Restore last access, 2 - Open the specified URL, 3 - Open the specified URL and the platform page simultaneously, 4 - Restore last access and the platform page simultaneously. This field is obsolete. |
| openLastPage | integer | Restore last visit 1 Yes 2 No |
| openSpecPage | integer | Open specified URL 1 Yes 2 No |
| openSiteUrl | bool | Open platform page |
| autoOpenUrls | array[string] | Specified URL |


### Simulation Information BrowserApiSearchSimpleSimulate


| Parameter Name | Type | Description |
| --- | --- | --- |
| os | integer | Operating system, 1: Win, 2: Mac |
| vendor | integer | Browser type, 1: Chrome |
| mixtureKey | string | Fingerprint algorithm ID |
| ua | string | User agent |
| uaVersion | string | Browser version, 0 represents all |
| timeZone | object | Time zone |
| timeZone.switcher | integer | 1: IP-based matching, 2: Custom, 3: Local timezone |
| timeZone.value | string | Custom value |
| webRtc | object | WebRTC |
| webRtc.switcher | integer | 1: Privacy, 2: Replace, 3: Real, 4: Disable |
| geoLocation | object | Geolocation |
| geoLocation.switcher | integer | 1: Ask, 2: Disable, 3: Allow |
| geoLocation.baseOnIp | bool | Match based on IP address |
| geoLocation.longitude | integer | Latitude |
| geoLocation.latitude | integer | Longitude |
| geoLocation.accuracy | integer | Accuracy (meters) |
| language | object | Language |
| language.switcher | integer | 1: IP-based matching, 2: Custom |
| language.value | string | A custom value, multiple values separated by commas |
| resolution | object | Resolution |
| resolution.switcher | integer | 1: random, 2: custom, 3: default |
| resolution.value | string | custom value |
| font | object | Font |
| font.switcher | integer | 1: Default, 2: Custom |
| canvas | object | Canvas |
| canvas.switcher | integer | 1: Noise, 2: Real |
| webglImage | object | WebGL Image |
| webglImage.switcher | integer | 1: Noise, 2: Real |
| webglMetadata | object | WebGL Metadata |
| webglMetadata.switcher | integer | 2: Disabled, 3: Custom |
| webglMetadata.provider | string | WebGL Provider |
| webglMetadata.render | string | WebGL Rendering |
| hardware | object | Hardware acceleration |
| hardware.switcher | integer | 1: Default, 2: Enabled, 3: Disabled |
| audioContext | object | AudioContext |
| audioContext.switcher | integer | 1: Noise, 2: Disabled |
| mediaDevice | object | Media device |
| mediaDevice.switcher | integer | 1: Noise, 2: Disabled |
| clientRects | object | ClientRects |
| clientRects.switcher | integer | 1: Noise, 2: Disabled |
| speechVoise | object | SpeechVoices |
| speechVoise.switcher | integer | 1: Noise, 2: Disabled |
| hardwareConcurrency | integer | Hardware concurrency |
| memoryDevice | integer | Device memory |
| doNotTrack | integer | Do Not Track 0: Default, 1: Enabled, 2: Disabled |
| bluetooth | object | Bluetooth |
| bluetooth.switcher | integer | 1: Private, 2: True |
| battery | object | Battery |
| battery.switcher | integer | 1: Private, 2: True |
| portScanProtection | object | Port scan protection |
| portScanProtection.switcher | integer | 1: Enable, 2: Disable |
| portScanProtection.value | string | Comma-separated list of ports allowed to be scanned |



## Error Code



Please refer to [Browser Error Codes](https://open.geelark.com/api/browser-error-codes).