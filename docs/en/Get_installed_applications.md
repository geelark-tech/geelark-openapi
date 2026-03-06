API Description
---------------

Retrieve the list of applications installed on the cloud phone.

Request URL
-----------

*   `https://openapi.geelark.com/open/v1/app/list`

Request Method
--------------

*   POST

Request Parameters
------------------

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| envId | Yes | string | Cloud phone environment ID | 123456654321 |
| page | Yes | integer | Page number, minimum is 1 | 1 |
| pageSize | Yes | integer | Number of items per page, minimum is 1, maximum is 100 | 10 |

Request Example
---------------

```json
{
    "envId" : "1809135651036667904",
    "page" : 1,
    "pageSize" : 5
}
```

Response Data Description
-------------------------

| Parameter Name | Type | Description |
| --- | --- | --- |
| total | integer | Total number of items |
| page | integer | Page number |
| pageSize | integer | Page size |
| items | array\[AppInfo\] | Array of application data |

### AppInfo

| Parameter Name | Type | Description |
| --- | --- | --- |
| appIcon | string | Application icon URL |
| appId | string | Application ID |
| appName | string | Application name |
| appVersionId | string | Application version ID |
| installStatus | int | Installation status: 0-Installing, 1-Installed, 2-Failed, 3-Uninstalling, 4-Uninstalled, 5-Uninstall Failed, others-Not Installed |
| installTime | string | Installation time |
| packageName | string | Application package name |
| versionCode | string | Application version code |
| versionName | string | Application version name |

Response Example
----------------

```json
{
    "traceId": "123",
    "code": 0,
    "msg": "success",
    "data": {
        "items": [
            {
                "appIcon": "http://cmp1-prod.zxpcloud.com/apps/io.tm.k.drama/K-DRAMA_1716451323126.png",
                "appId": "1793552962123993090",
                "appName": "K-DRAMA",
                "appVersionId": "1793552962140770305",
                "installStatus": 1,
                "installTime": "2024-07-10 23:07:56",
                "packageName": "io.tm.k.drama",
                "versionCode": "21120300",
                "versionName": "1.0.1"
            }
        ],
        "total": 1,
        "page": 1,
        "pageSize": 5
    }
}
```

Error Codes
-----------

The following are specific error codes for this API. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 42001 | The corresponding cloud phone does not exist |