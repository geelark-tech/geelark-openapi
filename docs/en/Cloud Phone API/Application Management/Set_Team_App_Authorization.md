[TOC]

## API Description

Grant team application permissions, including all permissions such as location permissions, which only apply to newly installed applications.

## Request URL


- `https://openapi.geelark.com/open/v1/app/auth/status`


## Request Method


- POST


## Request Parameters


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | Team application ID | 497652752864775437 |
| appAuth | Yes | integer | App authorization 0 disables authorization; 1 enables authorization | 1 |


## Request Example


```json
{
 &quot;id&quot;: &quot;497652752864775437&quot;,
 &quot;appAuth&quot;: 1
}
```


## Response Example


```json
{
 &quot;traceId&quot;: &quot;886A92FCBE9B7A52A7F583FCBD2BF6A8&quot;,
 &quot;code&quot;: 0,
 &quot;msg&quot;: &quot;success&quot;
}
```

## Error Codes


Please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

