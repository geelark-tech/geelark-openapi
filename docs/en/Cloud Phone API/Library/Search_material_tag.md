[TOC]

## Interface Description
search material tag


## Request URL

- `https://openapi.geelark.com/open/v1/material/tag/search`


## Request Method
- POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| page | No | int | page | Refer to Request Example  |
| pageSize | No | int | page size （max: 200） | Refer to Request Example  |
| name | No | string | search tag name | Refer to Request Example  |


## Request Example
```json
{
    &quot;page&quot; : 1,
    &quot;pageSize&quot; : 50 ,
    &quot;name&quot; : &quot;&quot;
}
```


## Response Example

```json
{
    &quot;traceId&quot;: &quot;8B6AC3809AAAE8099E94B124A7181BB9&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;total&quot;: 2,
        &quot;page&quot;: 1,
        &quot;pageSize&quot;: 50,
        &quot;list&quot;: [
            {
                &quot;id&quot;: &quot;569577514586891738&quot;,
                &quot;name&quot;: &quot;2&quot;,
                &quot;color&quot;: 4
            }
        ]
    }
}
```

## Response Data Description

| Parameter Name | Type              | Description          |
| ----------- | -----------|----------- 
| total | int | total data |
| page | int |current page  |
| pageSize | int | current page size  |
| list | array[TagData] | tag data |

## TagData Data Description

| Parameter Name | Type              | Description          |
| ----------- | -----------|----------- |
| id | int | tag id |
| name | int |tag id  |
| color | int | tag color: 0 White 1 Red 2 Blue 3 Green 4 Yellow 5 Purple |


## Error Codes

Below are specific error codes for the API. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).









