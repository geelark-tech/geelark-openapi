## API Description

Used to check the startup status of a specified browser. You need to specify the environment ID.

## Request URL

- `http://localhost:40185/api/v1/browser/status`

## Request Method

- POST

## Request Parameters

| Parameter | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | Browser ID | 539893235657500146 |

## Request Example

```json
{
"id": "539893235657500146"
}
```

## Response Example

```json
{
  "code": 0,
  "msg": "success",
  "data": {
    "status": "open", // Browser is running "open", if not running it is "close"
    "debugPort": 11000
  }
}
```

## Error Codes

For error codes, please refer to [API Call Instructions](https://open.geelark.cn/api/request-instructions)