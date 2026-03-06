[TOC]

## API Description

Get the application list

## Request URL

- `https://openapi.geelark.com/open/v1/app/shop/list`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| key | No | string | Search keyword | tiktok |
| getUploadApp | No | bool | Get uploaded apps | true |
| page | Yes | integer | Page number, minimum is 1 | 1|
| pageSize | Yes | integer | Number of data items per page, minimum is 1, maximum is 200 | 10|

## Request Example

```json
{
    &quot;key&quot; : &quot;tiktok&quot;,
	&quot;getUploadApp&quot; : false,
    &quot;page&quot; : 1,
    &quot;pageSize&quot; : 5
}
```

## Response Example

```json
{
	&quot;traceId&quot;:&quot;123&quot;,
	&quot;code&quot;:0,
	&quot;msg&quot;:&quot;success&quot;,
	&quot;data&quot;:{
		&quot;items&quot;:[
			{
				&quot;appIcon&quot;:&quot;http://cmp1-prod.zxpcloud.com/apps/io.tm.k.drama/K-DRAMA_1716451323126.png&quot;,
				&quot;appName&quot;:&quot;K-DRAMA&quot;,
				&quot;appVersionList&quot;:[
					{
						&quot;id&quot;:&quot;1793552962140770305&quot;,
						&quot;versionCode&quot;:21120300,
						&quot;versionName&quot;:&quot;1.0.1&quot;
					}
				],
				&quot;id&quot;:&quot;1793552962123993090&quot;
			}
		],
		&quot;total&quot;:1,
		&quot;page&quot;:1,
		&quot;pageSize&quot;:5
	}
}
```

## Response Data Description

| Parameter Name | Type | Description |
| ----------- | -----------|----------- |
| total | integer   | Total number  |
| page | integer   | Page number  |
| pageSize | integer   | Page size  |
| items | array[AmpAppInfo]   | Data array  |

### Application Information AmpAppInfo

| Parameter Name | Type | Description |
| ----------- | -----------|----------- |
| appIcon | string | Application icon |
| id | string | Application id |
| appName | string | Application name |
| appVersionList | array[AmpAppVersionInfo] | Application version information |

### Application version information AmpAppVersionInfo

| Parameter Name | Type | Description |
| ----------- | -----------|----------- |
| id | string | Application version id |
| versionCode | integer | Application version code |
| versionName | string | Application version name |

## Error Codes

Please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).
