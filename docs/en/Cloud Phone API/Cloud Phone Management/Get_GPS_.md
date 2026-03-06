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
    &quot;ids&quot;: [
        &quot;528086321789535232&quot;
    ]
}
```

## Response Example

```json
{
    &quot;traceId&quot;: &quot;81CA3BD0B7BBB924A1C6B836B298ADA7&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
        &quot;totalAmount&quot;: 1,
        &quot;successAmount&quot;: 1,
        &quot;failAmount&quot;: 0,
        &quot;list&quot;: [
            {
                &quot;id&quot;: &quot;528086321789535232&quot;,
                &quot;latitude&quot;: 1.3024300336837769,
                &quot;longitude&quot;: 103.87545776367188
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

### list GPS Information &lt;GPS&gt;
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
