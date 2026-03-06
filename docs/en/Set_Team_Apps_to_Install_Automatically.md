## API Description

Set up automatic installation for team applications. Once automatic installation is enabled, the applications will be installed after the cloud phone starts up.

## Request URL


- `https://openapi.geelark.com/open/v1/app/setStatus`


## Request Method


- POST


## Request Parameters


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | Team application ID | 497652752864775437 |
| status | Yes | integer | Whether to install automatically, 0 for no, 1 for yes | 1 |
| installGroupIds | No | array[string] | Allowed environment groups for installation, defaults to all environment groups, 0 represents no group | ["497652752864775437"] |

## Request Example


```json
{
 "id": "497652752864775437",
 "status": 1
}
```


## Response Example


```json
{
 "traceId": "886A92FCBE9B7A52A7F583FCBD2BF6A8",
 "code": 0,
 "msg": "success"
}
```

## Error Codes


Please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

