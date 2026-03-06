## API Description

Get the list of apps available for installation on the cloud phone.

## Request URL

*   `https://openapi.geelark.com/open/v1/app/installable/list`

## Request Method

*   POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| name | No | string | Search keyword | tiktok |
| envId | Yes | string | Cloud phone environment ID | 123456654321 |
| getUploadApp | No | bool | get upload app | true |
| page | Yes | integer | Page number, minimum is 1 | 1 |
| pageSize | Yes | integer | Number of items per page, minimum is 1, maximum is 100 | 10 |

## Request Example

```json
{
    "name" : "tiktok",
    "envId" : "1809135651036667904",
	"getUploadApp" : false,
    "page" : 1,
    "pageSize" : 5
}
```

## Response Body Description

| Parameter Name | Type | Description |
| --- | --- | --- |
| total | integer | Total number of tasks |
| page | integer | Page number |
| pageSize | integer | Page size |
| items | array\[AmpAppInfo\] | List of data items |

### Installable App Information `AmpAppInfo`

| Parameter Name | Type | Description |
| --- | --- | --- |
| appIcon | string | App icon URL |
| id | string | App ID |
| appName | string | App name |
| packageName | string | App package name |
| appVersionInfoList | array\[AmpAppVersionInfo\] | List of app versions |

### Installable App Version Information `AmpAppVersionInfo`

| Parameter Name | Type | Description |
| --- | --- | --- |
| id | string | App version ID |
| installStatus | int | Installation status: 0 - Installing, 1 - Installed, 2 - Installation Failed, 3 - Uninstalling, 4 - Uninstalled, 5 - Uninstallation Failed, others - Not Installed |
| versionCode | string | App version code |
| versionName | string | App version name |

## Response Example


```json
{
    "traceId": "123",
    "code": 0,
    "msg": "success",
    "data": {
        "items": [
            {
                "appIcon": "http://cmp1-prod.zxpcloud.com/apps/io.tm.k.drama/K-DRAMA_1716451323126.png",
                "appName": "K-DRAMA",
                "appVersionInfoList": [
                    {
                        "id": "1793552962140770305",
                        "installStatus": 1,
                        "versionCode": 21120300,
                        "versionName": "1.0.1"
                    }
                ],
                "id": "1793552962123993090",
                "installStatus": 1,
                "packageName": "io.tm.k.drama"
            }
        ],
        "total": 1,
        "page": 1,
        "pageSize": 5
    }
}
```

## Error Codes

The following are specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 42001 | The specified cloud phone does not exist |