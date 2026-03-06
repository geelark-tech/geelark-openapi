[TOC]

## API Description

Get account data

## Request URL

*    `https://openapi.geelark.com/open/v1/analytics/data`

## Request Method

*   POST

## Request Parameters

### Query Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| page   | Yes   | integer | page | 1 |
| pageSize   | Yes   | integer | page size（1-100） | 10 |
| account   | No   | string | account| tk_acc |
| dataDate   | No   | integer | search date timestamp | 1764136841 |
| createdId   | No   | string | user add account user id  | 547236295441737181 |
| channel   | No   | integer | account channel, 0: TikTok 1:YouTube 2:Instagram | 1 |

## Request Example
```json
{
	&quot;account&quot; : &quot;tk_acc&quot;,
	&quot;dataDate&quot; : 1764137986,
	&quot;createdId&quot; : &quot;497521349330210656&quot;,
	&quot;channel&quot; : 1,
	&quot;page&quot; : 1,
	&quot;pageSize&quot; : 10
}
```

## Response Data Description

| Parameter Name | Type | Description |
| --- | --- | --- |
| total    | integer               | total |
| page  | integer               | current page      |
| pageSize     | integer               | current page size     |


### successDetails Success Information &lt;items&gt;

| Parameter Name | Type | Description |
| --- | --- | --- |
| id    | string               | account id |
| channel  | integer               | account channel     |
| account     | string               | account     |
| playCount     | integer               | play count ,  -1 indicates that the data has not been updated yet|
| followerCount     | integer               | follower count  ,  -1 indicates that the data has not been updated yet    |
| diggCount     | integer               | digg count  ,  -1 indicates that the data has not been updated yet    |
| commentCount     | integer               | comment count   ,  -1 indicates that the data has not been updated yet   |
| collectCount     | integer               | collect count   ,  -1 indicates that the data has not been updated yet   |
| shareCount     | integer               | share count  ,  -1 indicates that the data has not been updated yet    |
| dataDate     | integer               | data date     |
| addAccDate     | integer               | add account date     |
| remark     | string               | remark     |
| createdId     | string               | add account user id     |
| username     | string               | add account username     |


## Response Example

```json
{
	&quot;traceId&quot;: &quot;B8899554AA90BB168406A5CB8A089AB2&quot;,
	&quot;code&quot;: 0,
	&quot;msg&quot;: &quot;success&quot;,
	&quot;data&quot;: {
		&quot;total&quot;: 2,
		&quot;page&quot;: 1,
		&quot;pageSize&quot;: 10,
		&quot;items&quot;: [
			 {
				 &quot;id&quot;: &quot;581465531480044822&quot;,
				 &quot;channel&quot;: 0,
				 &quot;account&quot;: &quot;khian.kb&quot;,
				 &quot;playCount&quot;: -1,
				 &quot;followerCount&quot;: -1,
				 &quot;diggCount&quot;: -1,
				 &quot;commentCount&quot;: -1,
				 &quot;collectCount&quot;: -1,
				 &quot;shareCount&quot;: -1,
				 &quot;dataDate&quot;: -1,
				 &quot;addAccDate&quot;: 1756110064,
				 &quot;remark&quot;: &quot;&quot;,
				 &quot;createdId&quot;: &quot;497521349330210656&quot;,
				 &quot;username&quot;: &quot;exlrhoo@foxmail.com&quot;
			 }
		 ]
	}
}
```

## Error Codes

Below are specific error codes for this interface. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 43002  | please upgrade to pro package, then try again   |