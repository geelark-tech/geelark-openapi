[TOC]

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
 &quot;page&quot; : 1,
 &quot;pageSize&quot; : 5
}
```


## Response Example


```json
{
	&quot;traceId&quot;:&quot;97CBBCCB8DAFC8D1BDEFB943945BFC95&quot;,
	&quot;code&quot;:0,
	&quot;msg&quot;:&quot;success&quot;,
	&quot;data&quot;:{
		&quot;total&quot;:4,
		&quot;page&quot;:1,
		&quot;pageSize&quot;:1,
		&quot;items&quot;:[
			{
				&quot;id&quot;:&quot;497652752864775437&quot;,
				&quot;appName&quot;:&quot;TikTok&quot;,
				&quot;appIcon&quot;:&quot;https://material.geelark.cn/app/icon/20251026/kVAQ8OuTNF.png&quot;,
				&quot;versionId&quot;:&quot;1793552962123993090&quot;,
				&quot;versionCode&quot;:410903,
				&quot;versionName&quot;:&quot;41.9.3&quot;,
				&quot;status&quot;:0,
				&quot;isUpload&quot;:false,
				&quot;uploadStatus&quot;:0,
				&quot;appAuth&quot;:0,
				&quot;appRoot&quot;:0,
				&quot;envGroups&quot;:[]
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

