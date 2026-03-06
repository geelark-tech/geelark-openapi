[TOC]

## API Description

Enable or disable team application ROOT

## Request URL


- `https://openapi.geelark.com/open/v1/app/root`


## Request Method


- POST


## Request Parameters


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | Team application ID | 497652752864775437 |
| opera | Yes | integer | Operation, 0 off, 1 on | 1 |


## Request Example


```json
{
 &quot;id&quot;: &quot;497652752864775437&quot;,
 &quot;opera&quot;: 1
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

