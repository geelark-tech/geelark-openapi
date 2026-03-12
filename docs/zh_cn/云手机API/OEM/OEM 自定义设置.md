## 接口说明
自定义设置云手机左上角品牌名、品牌Logo、侧边栏入口、二维码域名等。
- `该功能需套餐环境数≥50，自动解锁`


## 请求URL


- `https://openapi.geelark.cn/open/v1/phone/customization`


## 请求方法


- POST


## 请求参数


| 参数名 | 必选 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- | --- |
| title | 否 | string | 标题，限制64字节，不填或者填空保持原值不变 | 参考请求示例 |
| logo | 否 | string | logo链接，限制255字节，不填或者填空保持原值不变 | 参考请求示例 |
| hideHeader | 否 | bool | 是否隐藏云机顶部的header，不填默认false | true |
|mirrorUrl|否|string|接力入口内二维码和手机打开的链接地址，限制255字节，不填或者填空保持原值不变，设置后GeeLark将在接力入口内显示该地址（如红框所示）![示例](https://material.geelark.cn/mirror_url_demo.jpg.jpg "示例")用户访问此地址时请将带上所有参数重定向到(建议使用iframe) https://mobile.geelark.cn/mobile.html|参考请求示例|
| toolBarSettings | 否 | array[ToolBarSettings] | 控制云手机侧边工具栏入口是否显示，未设置则默认全部显示 | 参考请求示例 |

### ToolBarSettings
| 参数名 | 类型 | 说明 |
| --- | --- | --- |
| toolBar | string | 设置项名称，请参考下面的设置项说明 |
| visible | bool | 是否显示，不填或者填false则为不显示 |

#### 设置项说明
*   `networkQuality`: 网络质量信号灯
*   `rotate`：旋转
*   `screenshot`：截图
*   `upload`：文件上传
*   `library`: 资源库，只有在 `upload` 显示的时候，设置为隐藏才有效
*   `volumeUp`：音量+
*   `volumeDown`：音量-
*   `speedUp`：加速
*   `detection`：(网络)检测
*   `quality`：清晰度
*   `restart`：重启
*   `apk`：应用(管理)
*   `qcode`：二维码
*   `export`: 导出
*   `timing`: 计时
*   `liveStreaming`：直播(/录播)
*   `clear`: 清理

## 请求示例
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



## 响应示例


```json
{
    "traceId": "ADD9A7489BB2198DBC0FB37082684CB0",
    "code": 0,
    "msg": "success"
}
```


## 错误码


以下为接口特定错误码，其他错误码请参考[云手机错误码](https://open.geelark.cn/api/cloud-phone-error-codes)


| 错误码 | 说明 |
| --- | --- |
| 40015 | 权限限制 |
| 60003 | 非法的链接 |
| 60004 | 文件格式不支持 |