## API Description
- Generate a new cloud phone of the same model, retains the country, time zone, language, and GPS information. Applications and data will be cleared.

## Request URL

- `https://openapi.geelark.com/open/v1/phone/clone`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type | Description |
| --- | --- | --- | --- | --- |
|envId|Yes|string|The ID of the cloud phone to be cloned|
|amount|Yes|int|The number of clones, ranging from 1 to 100|
|groupId|No|string|The ID of the target group. If not specified, the phone will be placed in an ungrouped area|
|cloneName|No|bool|Whether to clone the name|
|cloneRemark|No|bool|Whether to clone the remark|
|cloneTag|No|bool|Whether to clone the tag|
|cloneProxy|No|bool|Whether to clone the proxy|
|cloneNetType|No|bool|Whether to clone the network type|

## Request Example

```json
{
    "envId": "590711571886417452",
	"amount": 1,
    "groupId": "590711571886417453"
}
```

## Response Body Data Description

| Parameter Name       |     Type   |     Description    |
| ----------- | -----------|----------- |
| ids | array[string] | Cloned cloud phone ID|

## Response Example

```json
{
    "traceId": "B3DAFF64A7BD493CB1169D94A22BFC8D",
    "code": 0,
    "msg": "success",
    "data": {
        "ids": [
            "590711571886417454"
        ]
    }
}
```

## Error Codes

The following are API-specific error codes. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 44001 | Pro Package Limit |
| 42001 | Corresponding Cloud Machine Does Not Exist |
| 43032 | Group Does Not Exist |
| 44002 | Package Environment Quantity Limit Reached |
| 44004 | Today's Environment Creation Limit Reached |
| 44006 | Insufficient Cloud Phone Inventory |
| 43038 | Device Model Deleted |