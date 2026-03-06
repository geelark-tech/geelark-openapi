[TOC]

## Interface Description
- Set/update the GPS information of cloud phones, including longitude and latitude.
- Longitude range: `[-180.0, 180.0]`
- Latitude range: `[-90.0, 90.0]`

## Request URL
- `https://openapi.geelark.com/open/v1/phone/gps/set`

## Request Method
- POST

## Request Parameters
| Parameter Name | Required | Type       | Description           | Example           |
| -------------- | -------- | ---------- | --------------------- | ----------------- |
| list           | Yes      | array[GPS] | Cloud phone GPS info  | Refer to Request Example |

### list Cloud Phone GPS Info &lt;GPS&gt;
| Parameter Name | Required | Type   | Description | Example           |
| -------------- | -------- | ------ | ----------- | ----------------- |
| id             | Yes      | string | Cloud phone ID | Refer to Request Example |
| longitude      | Yes      | float  | Longitude    | Refer to Request Example |
| latitude       | Yes      | float  | Latitude     | Refer to Request Example |

## Request Example
```json
{
    &quot;list&quot;: [
        {
            &quot;id&quot;: &quot;528086321789535232&quot;,
            &quot;latitude&quot;: 1.30243,
            &quot;longitude&quot;: 103.87546
        },
        {
            &quot;id&quot;: &quot;530011895768286208&quot;,
            &quot;latitude&quot;: 11.30243,
            &quot;longitude&quot;: 104.87546
        }
    ]
}
```

## Response Example
```json
{
    &quot;traceId&quot;: &quot;870AE3259C965B45A0D09C92A4EA8F81&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;totalAmount&quot;: 2,
        &quot;successAmount&quot;: 2,
        &quot;failAmount&quot;: 0
    }
}
```

### Response Data Description
| Parameter Name | Type    | Description          |
| -------------- | ------- | -------------------- |
| totalAmount    | integer | Total number of requested IDs |
| successAmount  | integer | Total number of successful requests |
| failAmount     | integer | Total number of failed requests |

## Error Codes
Below are the specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 42001      | Cloud phone does not exist         |
| 43012      | Latitude/longitude range error     |
