## Interface Description
For anyone who want to integrate the 1st and world's best cloud phone, feel free to do it. Contact us if you need any help regarding integration.

Customize the brand name, brand logo, sidebar entrance, QR code domain name, etc.
- `You can access this feature when your plan includes 50 or more profiles.`


## Request URL


- `https://openapi.geelark.com/open/v1/phone/customization`


## Request Method


- POST


## Request Parameters


| Parameter Name | Required | Type          | Description           | Example           |
| -------------- | -------- | ------------- | --------------------- | ----------------- |
| title | No | string | Title, maximum length 64 bytes. If not provided or left empty, the original value remains unchanged. |  Refer to Request Example |
| logo | No | string |Logo URL, maximum length 255 bytes. If not provided or left empty, the original value remains unchanged.|  Refer to Request Example |
| hideHeader | No | bool | Whether to hide the header at the top of the cloud phone. Defaults to false if not provided|  false|
|mirrorUrl|No|string|The QR code and the url opened on the phone's browser in the "Mirror" entrance, limited to 255 characters. if set this value, GeeLark will display the url in the "Mirror" entrance (as shown picture blow).![demo](https://singapore-upgrade.geelark.cn/en_mirror_url_demo.jpg "demo") When open this url, please redirect to https://mobile.geelark.com/mobile.html with all parameters (it is recommended to use a iframe) )|Refer to Request Example|
| toolBarSettings | No | array[ToolBarSettings] | Control whether the toolbar entrance on the side of the cloud phone should displayed. If not set, all will be displayed by default. | See request example |

### ToolBarSettings
| Parameter | Type | Description |
| --- | --- | --- |
| toolBar | string | Toolbar item name. Refer to the item descriptions below. |
| visible | bool | Whether to display the item. If omitted or set to false, the item will not be displayed. |

#### Toolbar Item Descriptions
*   `networkQuality`: Network quality indicator
*   `rotate`: Rotate
*   `screenshot`: Screenshot
*   `upload`: File upload
*   `library`: library. This setting takes effect only when upload is visible; hiding it is effective only in that case.
*   `volumeUp`: Volume up
*   `volumeDown`: Volume down
*   `speedUp`: Speed up
*   `detection`: Network detection
*   `quality`: Video quality
*   `restart`: Restart
*   `apk`: Application (management)
*   `qcode`: QR code
*   `export`: Export
*   `timing`: Timer
*   `liveStreaming`: Live streaming (recording)
*   `clear`: Clear


## Request Example
```json
{
    "logo": "https://material.geelark.cn/user-upload/banner0903_cn.jpg",
    "title": "GeeLark",
    "hideHeader": false,
    "mirrorUrl": "https://www.abcd.com/mirror/url",
	"toolBarSettings": [
        {
            "toolBar": "networkQuality",
            "visible": false
        },
		 {
            "toolBar": "rotate",
            "visible": false
        },
		 {
            "toolBar": "screenshot",
            "visible": false
        },
		 {
            "toolBar": "upload",
            "visible": true
        },
		 {
            "toolBar": "library",
            "visible": false
        },
		 {
            "toolBar": "volumeUp",
            "visible": false
        }
    ]
}
```


## Response Example


```json
{
    "traceId": "ADD9A7489BB2198DBC0FB37082684CB0",
    "code": 0,
    "msg": "success"
}
```



## Error Codes


Below are the specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).


| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 40015 | Permission limit |
| 60003 | Illegal url |
| 60004 | Invalid file format |