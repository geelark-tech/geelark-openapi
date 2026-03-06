[TOC]

## Request URL

- `https://openapi.geelark.com/open/v1/analytics/accounts/update`

## Request Method

- POST

## Request Parameters

| Parameter | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | Account ID | 565523829426802069 |
| account | No | string | Platform account, maximum 64 characters | myAccount |
| channel | No | int | Platform | 0: TikTok 1: YouTube 2: Instagram |
| remark | No | string | Remark | myRemark |

## Request Example

```json
{
    &quot;id&quot;: &quot;565523829426802069&quot;,
    &quot;account&quot;: &quot;abc&quot;
}
```

## Response Example

```json
{
    &quot;traceId&quot;: &quot;9D1A84D6A2A8F9A8A5CD9BA7B7E84281&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;
}
```
