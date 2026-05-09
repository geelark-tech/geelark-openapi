## Interface Description


Create a new browser, support configuration of platform account password and cookies, proxy ID and proxy information, fingerprint information, etc. After successful creation, the browser environment ID is returned.



## Request URL


- `http://localhost:40185/api/v1/browser/create`


## Request method



- POST



## Request Parameters



| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| serialName | Yes | string | Environment name, up to 100 characters | myBrowser |
| groupId | No | string | Environment group ID | 497548067550006541 |
| tagIds | No | array[string] | Environment tag IDs | ["497548067550006541"] |
| remark | No | string | Environment remark, up to 1500 characters | myRemark |
| cookie | No | string | Cookie, supports JSON and Netscape formats | [{"domain":".example.com","expires":"2025-12-31T23:59:59Z","httpOnly":true,"name":"SESSION_ID","path":"/","sameSite":"Lax","secure":true,"value":"a1b2c3d4e5f67890abcdef1234567890"}] |
| accountPlatform | No | string | Account platform. Only supports https://www.tiktok.com/ and https://www.facebook.com/ | https://www.tiktok.com/ |
| accountUsername | No | string | Account username | myUser |
| accountPassword | No | string | Account password | myPass |
| accountTOTPSecret | No | string | Account 2FA key | 7J64V3P3E77J3LKNUGSZ5QANTLRLTKVL |
| openLastPage | No | integer | Whether to restore the last visit, 1-Yes, 2-No, default is No | 1 |
| openSpecPage | No | integer | Whether to open the specified URL, 1-Yes, 2-No, default is No | 1 |
| openTabs | No | string | Opens specified web pages. Separate multiple tabs with ;. | http://www.b.com |
| browserOs | Yes | integer | Operating system, 1-win, 2-mac | 1 |
| browserUa | No | string | userAgent, if not passed, a random value will be used | Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/136.0.7103.93 Safari/537.36 |
| simulateConfig | No | SimulateConfig | Simulation configuration, if not passed, a random value will be used | See SimulateConfig |
| proxyId | No | string | Proxy ID, preferred | 497548067550006541 |
| proxyConfig | No | BrowserApiAddProxy | Proxy information | See BrowserApiAddProxy |
| browserStartArg | No | string | Startup parameters | -disable-popups |


###  Simulation Configuration SimulateConfig


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| timeZone | Yes | object | Time zone | - |
| timeZone.switcher | Yes | integer | 1: Matched by IP address, 2: Custom, 3: Local time zone | 2 |
| timeZone.value | Yes | string | Custom value, refer to [Browser Timezone](https://singapore-upgrade.geelark.cn/apiResource/browser_timezone.txt) | GMT-12:00 Etc/GMT+12 |
| language | Yes | object | Language | - |
| language.switcher | Yes | integer | 1: Matched by IP address, 2: Custom | 2 |
| language.value | Yes | string | Custom value, multiple values separated by commas, refer to [Browser Language](https://singapore-upgrade.geelark.cn/apiResource/browser_language.txt) | Albanian |
| resolution | Yes | object | Resolution | - |
| resolution.switcher | Yes | integer | 1: Random, 2: Custom, 3: Default | 2 |
| resolution.value | Yes | string | Custom value, refer to [browser resolution](https://singapore-upgrade.geelark.cn/apiResource/browser_resolution.txt) | 750*1334 |
| webRtc | yes | object | WebRTC | - |
| webRtc.switcher | yes | integer | 1: Privacy, 2: Replace, 3: True, 4: Disable | 1 |
| geoLocation | yes | object | Geolocation | - |
| geoLocation.switcher | yes | integer | 1: Ask, 2: Disable, 3: Allow | 1 |
| geoLocation.baseOnIp | yes | bool | Match based on IP | true |
| geoLocation.longitude | yes | integer | Latitude | 10 |
| geoLocation.latitude | yes | integer | Longitude | 20 |
| geoLocation.accuracy | yes | integer | Accuracy (meters) | 10 |
| canvas | yes | object | Canvas | - |
| canvas.switcher | yes | integer | 1: Noise, 2: True | 1 |
| webglImage | yes | object | WebGL Image | - |
| webglImage.switcher | Yes | integer | 1: Noise, 2: Real | 1 |
| hardware | Yes | object | Hardware Acceleration | - |
| hardware.switcher | Yes | integer | 1: Default, 2: Enabled, 3: Disabled | 1 |
| audioContext | Yes | object | AudioContext | - |
| audioContext.switcher | Yes | integer | 1: Noise, 2: Disabled | 1 |
| mediaDevice | Yes | object | Media Device | - |
| mediaDevice.switcher | Yes | integer | 1: Noise, 2: Disabled | 1 |
| clientRects | Yes | object | ClientRects | - |
| clientRects.switcher | Yes | integer | 1: Noise, 2: Disabled | 1 |
| speechVoise | Yes | object | SpeechVoices | - |
| speechVoise.switcher | Yes | integer | 1: Noise, 2: Off | 1 |
| hardwareConcurrency | Yes | integer | Hardware concurrency | 26 |
| memoryDevice | Yes | integer | Device memory | 8 |
| doNotTrack | Yes | integer | Do Not Track 0: Default, 1: On, 2: Off | 2 |
| bluetooth | Yes | object | Bluetooth | - |
| bluetooth.switcher | Yes | integer | 1: Privacy, 2: True | 1 |
| battery | Yes | object | Battery | - |
| battery.switcher | Yes | integer | 1: Privacy, 2: True | 1 |
| portScanProtection | Yes | object | Port scan protection | - |
| portScanProtection.switcher | Yes | integer | 1: Enable, 2: Disable | 1 |
| portScanProtection.value | Yes | string | Ports allowed to be scanned, comma separated | 80 |


### Proxy Information BrowserApiAddProxy


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| typeId | yes | integer | Proxy type ID. -1 represents a direct connection. | 1 |
| server | no | string | Proxy host | server.com |
| port | no | integer | Proxy port | 1234 |
| username | no | string | Proxy username | user |
| password | no | string | Proxy password | password |
| country | no | string | Dynamic proxy country | us |
| region | no | string | Dynamic proxy region | alabama |
| city | no | string | Dynamic proxy city | mobile |
| useProxyCfg | no | bool | Whether to use the configured dynamic proxy. | true |
| protocol | no | integer | Dynamic proxy protocol. 1 represents socks5, 2 represents http. | 1 |


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
    "serialName":"myBrowserName",
    "browserOs":1,
    "proxyConfig":{
        "typeId":-1
    },
    "simulateConfig":{
        "timeZone": {
            "switcher": 2,
            "value": "GMT-12:00 Etc/GMT+12"
        },
        "language": {
            "switcher": 2,
            "value": "Albanian"
        },
        "resolution": {
            "switcher": 2,
            "value": "750*1334"
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
        "canvas":{
            "switcher":1
        },
        "webglImage":{
            "switcher":1
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
```



## Example response



```json
{
    "traceId":"123456ABCDEF",
    "code":0,
    "msg":"success",
    "data":{
        "id":"497548067550006541"
    }
}
```



## Response body data description



| Parameter Name | Type | Description |
| --- | --- | --- |
| id | string | Environment ID |



## Error Code



Below are specific error codes for this interface. For other error codes, please refer to [Browser Error Codes](https://open.geelark.com/api/browser-error-codes).



| Error Code | Description |
| --- | --- |
| 44002 | The maximum number of package environments has been reached |
| 44003 | The maximum number of user environments has been reached |
| 44004 | The maximum number of environments created today has been reached |
| 45006 | Incorrect proxy information |
| 45003 | Proxy not allowed |
| 45004 | Proxy verification failed |
| 43028 | The sub-user does not have permissions for this environment group |