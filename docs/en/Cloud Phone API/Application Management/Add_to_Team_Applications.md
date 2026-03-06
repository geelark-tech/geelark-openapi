[TOC]

## API Description

Add the app to the team Applications and it will be automatically installed after the cloud phone is started

## Request URL

- `https://openapi.geelark.com/open/v1/app/add`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | yes | string | Application id; Please call the “Get Application List” API to obtain it. | 1793552962123993090 |
| versionId | yes | string | Version id; Please call the “Get Application List” API to obtain it. | 1793552962140770305 |
| installGroupIds | no | array[string] | Environment groups allowed for installation. Defaults to all environment groups. &quot;0&quot; indicates no grouping;Please call the query group API first to obtain the group ID. | [&quot;528715748189668352&quot;] |

## Request Example

```json
{
 &quot;id&quot;: &quot;1793552962123993090&quot;,
 &quot;versionId&quot;: &quot;1793552962140770305&quot;,
 &quot;installGroupIds&quot;: [&quot;0&quot;]
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
