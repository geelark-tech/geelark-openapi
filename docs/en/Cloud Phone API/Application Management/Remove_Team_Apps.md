[TOC]

## API Description

Remove the application from the team applications.

## Request URL


- `https://openapi.geelark.com/open/v1/app/remove`


## Request Method


- POST


## Request Parameters


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | Team application ID | 497652752864775437 |


## Request Example


```json
{
 &quot;id&quot;: &quot;497652752864775437&quot;
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

