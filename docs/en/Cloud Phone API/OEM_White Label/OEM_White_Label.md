[TOC]



## Interface Description
For anyone who want to integrate the 1st and world&#039;s best cloud phone, feel free to do it. Contact us if you need any help regarding integration.

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
|mirrorUrl|No|string|The QR code and the url opened on the phone&#039;s browser in the &quot;Mirror&quot; entrance, limited to 255 characters. if set this value, GeeLark will display the url in the &quot;Mirror&quot; entrance (as shown picture blow).![demo](https://singapore-upgrade.geelark.cn/en_mirror_url_demo.jpg &quot;demo&quot;) When open this url, please redirect to https://mobile.geelark.com/mobile.html with all parameters (it is recommended to use a iframe) )|Refer to Request Example|
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
    &quot;logo&quot;: &quot;https://material.geelark.cn/user-upload/banner0903_cn.jpg&quot;,
    &quot;title&quot;: &quot;GeeLark&quot;,
    &quot;hideHeader&quot;: false,
    &quot;mirrorUrl&quot;: &quot;https://www.abcd.com/mirror/url&quot;,
	&quot;toolBarSettings&quot;: [
        {
            &quot;toolBar&quot;: &quot;networkQuality&quot;,
            &quot;visible&quot;: false
        },
		 {
            &quot;toolBar&quot;: &quot;rotate&quot;,
            &quot;visible&quot;: false
        },
		 {
            &quot;toolBar&quot;: &quot;screenshot&quot;,
            &quot;visible&quot;: false
        },
		 {
            &quot;toolBar&quot;: &quot;upload&quot;,
            &quot;visible&quot;: true
        },
		 {
            &quot;toolBar&quot;: &quot;library&quot;,
            &quot;visible&quot;: false
        },
		 {
            &quot;toolBar&quot;: &quot;volumeUp&quot;,
            &quot;visible&quot;: false
        }
    ]
}
```


## Response Example


```json
{
    &quot;traceId&quot;: &quot;ADD9A7489BB2198DBC0FB37082684CB0&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;
}
```



## Error Codes


Below are the specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).


| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 40015 | Permission limit |
| 60003 | Illegal url |
| 60004 | Invalid file format |



