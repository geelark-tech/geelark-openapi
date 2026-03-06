[TOC]

## API Description

Batch operation of applications on opened cloud phone

## Request URL


- `https://openapi.geelark.com/open/v1/app/operation/batch`


## Request Method


- POST


## Request Parameters


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| action | Yes | interger | Operation type 1 Startup; 2. Close; 3. Restart; 4 Installation; 5 Uninstalling | 1 |
| groupIds | No | array[string] | Group ID, operate on the opened cloud phone under the specified group, default to all | [&quot;595681312937911830&quot;] |
| packageName | No | string | Application package name, startup/close/restart/uninstall, choose between packageName/versionId , recommended to use package name | io.tm.k.drama |
| versionId | No| string | Application version ID, required for installation, can be obtained through the/app/teamApp/list interface |1793552962140770305 |


### Request Example


Startup
```json
{
    &quot;action&quot; : 1,
    &quot;groupIds&quot; : [&quot;595681312937911830&quot;],
    &quot;packageName&quot;: &quot;io.tm.k.drama&quot;
}
```

Installation
```json
{
    &quot;action&quot; : 1,
    &quot;groupIds&quot; : [&quot;595681312937911830&quot;],
    &quot;versionId&quot;: &quot;1793552962140770305&quot;
}
```

## Response Data Description

### items 
| Parameter Name | Type | Description |
| --- | --- | --- |
| id | integer   | cloud phone id  |
| errCode | integer   | Error code 1: The application is currently being installed/uninstalled; 2 corresponding apps not installed  |

### Response Example


```json
{
    &quot;traceId&quot;: &quot;A0598A2CA0802A98957B9E1F87EB9289&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;items&quot;: [
            {
                &quot;id&quot;: &quot;583502967211075086&quot;,
                &quot;errCode&quot;: 2
            }
        ]
    }
}
```

## Error Codes


Please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

