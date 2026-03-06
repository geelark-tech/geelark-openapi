## API Description

Get Team Application List

## Request URL


- `https://openapi.geelark.com/open/v1/app/teamApp/list`


## Request Method


- POST


## Request Parameters


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| page | Yes | Integer | Page number, minimum is 1 | 1|
| pageSize | Yes | Integer | Number of records per page, minimum is 1, maximum is 200 | 10|


## Request Example


```json
{
 "page" : 1,
 "pageSize" : 5
}
```


## Response Example


```json
{
	"traceId":"97CBBCCB8DAFC8D1BDEFB943945BFC95",
	"code":0,
	"msg":"success",
	"data":{
		"total":4,
		"page":1,
		"pageSize":1,
		"items":[
			{
				"id":"497652752864775437",
				"appName":"TikTok",
				"appIcon":"https://material.geelark.cn/app/icon/20251026/kVAQ8OuTNF.png",
				"versionId":"1793552962123993090",
				"versionCode":410903,
				"versionName":"41.9.3",
				"status":0,
				"isUpload":false,
				"uploadStatus":0,
				"appAuth":0,
				"appRoot":0,
				"envGroups":[]
			}
		]
	}
}
```


## Response Data Description


| Parameter Name | Type | Description |
| ----------- | -----------|----------- |
| total | integer | Total number |
| page | integer | Page number |
| pageSize | integer | Page size |
| items | array[AppTeamAppListItem] | Data array |

### Application Information AppTeamAppListItem

| Parameter Name | Type | Description |
| ----------- | -----------|----------- |
| id | string | Team application ID |
| appName | string | Application name |
| appIcon | string | Application icon |
| versionId | string | Version ID |
| versionCode | integer | Version number |
| versionName | string | Version name |
| status | integer | Whether to install automatically, 0 for no, 1 for yes |
| isUpload | bool | Application being uploaded |
| uploadStatus | integer | Upload status, 0 for uploading, 1 for successful upload, 2 for failed upload, 3 for failed review |
| appAuth | integer | App authorization, 0 for off authorization, 1 for on authorization |
| appRoot | integer | App root, 0 for off, 1 for on |
| envGroups | array[string] | Allowed environment group IDs, empty represents all environment groups, 0 represents no group |

## Error Codes


Please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

