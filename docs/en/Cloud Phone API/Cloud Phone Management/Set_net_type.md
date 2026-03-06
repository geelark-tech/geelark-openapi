[TOC]

## API Description

Set up the cloud phone network connection mode

## Request URL


- `https://openapi.geelark.com/open/v1/phone/net/set`


## Request Method


- POST


## Request Parameters


| Parameter Name | Required | Type | Description                 |
| ----------- | ---- | ------------- | -------------------- |
| id          | Yes   | string        | Cloud Phone ID            |
| netType | Yes | integer | Networking. 0-Wi-Fi, 1-Mobile. Only supported on Android 12/Android 13/Android 15 |


## Request Example


```json
{
  &quot;id&quot;: &quot;528086284158239744&quot;,
  &quot;netType&quot;: 0
}
```


## Response Example


```json
{
  &quot;traceId&quot;: &quot;B04B0843BD86D9589AB3BAB6A9EA3D92&quot;,
  &quot;code&quot;: 0,
  &quot;msg&quot;: &quot;success&quot;
}
```

## Error Codes

For error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 42001 | cloud phone not found |
