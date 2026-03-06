[TOC]

## Interface Description

- Query the GPS information of cloud phones, including latitude and longitude.

## Request URL

- `https://openapi.geelark.com/open/v1/phone/gps/get`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type          | Description               | Example           |
| -------------- | -------- | ------------- | ------------------------- | ----------------- |
| ids            | Yes      | array[string] | List of cloud phone IDs   | Refer to Request Example |

## Request Example

```json
{
    "ids": [
        "528086321789535232"
    ]
}
```

## Response Example

```json
{
    "traceId": "81CA3BD0B7BBB924A1C6B836B298ADA7",
    "code": 0,
    "msg": "success",
    "data": {
        "totalAmount": 1,
        "successAmount": 1,
        "failAmount": 0,
        "list": [
            {
                "id": "528086321789535232",
                "latitude": 1.3024300336837769,
                "longitude": 103.87545776367188
            }
        ]
    }
}
```

## Response Data Description

| Parameter Name | Type    | Description          |
| -------------- | ------- | -------------------- |
| totalAmount    | integer | Total number of requested IDs |
| successAmount  | integer | Total number of successful requests |
| failAmount     | integer | Total number of failed requests |
| list           | GPS     | GPS information      |

### list GPS Information <GPS>
| Parameter Name | Type    | Description          |
| -------------- | ------- | -------------------- |
| id             | string  | Cloud phone ID       |
| latitude       | float   | Latitude             |
| longitude      | float   | Longitude            |

## Error Codes

Below are the specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 42001      | Cloud phone does not exist         |
