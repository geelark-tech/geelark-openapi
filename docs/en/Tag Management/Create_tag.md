[TOC]

## Interface Description

- Create tags with specified **name and color (optional)**.
- Support batch creation.
- If no color is selected during creation, the default color is **white**.

### Color List

- `white`
- `red`
- `blue`
- `green`
- `yellow`
- `purple`

## Request URL

- `https://openapi.geelark.com/open/v1/tag/add`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type          | Description       | Example           |
| -------------- | -------- | ------------- | ----------------- | ----------------- |
| list           | Yes      | array[TagItem] | Tag data list     | Refer to Request Example |

### list Data List &lt;TagItem&gt;

| Parameter Name | Required | Type   | Description | Example                   |
| -------------- | -------- | ------ | ----------- | ------------------------- |
| name           | Yes      | string | Tag name, up to 30 characters    | tag                       |
| color          | No       | string | Tag color   | white, see color list for details |

## Request Example

```json
{
  &quot;list&quot;: [
    {
      &quot;name&quot;: &quot;tagEmpty&quot;
    },
    {
      &quot;name&quot;: &quot;tagRed&quot;,
      &quot;color&quot;: &quot;red&quot;
    },
    {
      &quot;name&quot;: &quot;tagBlue&quot;,
      &quot;color&quot;: &quot;blue&quot;
    },
    {
      &quot;name&quot;: &quot;tagGreen&quot;,
      &quot;color&quot;: &quot;green&quot;
    },
    {
      &quot;name&quot;: &quot;tagYellow&quot;,
      &quot;color&quot;: &quot;yellow&quot;
    },
    {
      &quot;name&quot;: &quot;tagPurple&quot;,
      &quot;color&quot;: &quot;purple&quot;
    },
    {
      &quot;name&quot;: &quot;tagWhite&quot;,
      &quot;color&quot;: &quot;white&quot;
    },
    {
      &quot;name&quot;: &quot;tagWhite2&quot;,
      &quot;color&quot;: &quot;&quot;
    },
    {
      &quot;name&quot;: &quot;tagInvalid&quot;,
      &quot;color&quot;: &quot;abc&quot;
    }
  ]
}
```

## Response Example

```json
{
  &quot;traceId&quot;: &quot;BC78266DA98F18EA9278B9C89AF9BB9B&quot;,
  &quot;code&quot;: 0,
  &quot;msg&quot;: &quot;success&quot;,
  &quot;data&quot;: {
    &quot;totalAmount&quot;: 9,
    &quot;successAmount&quot;: 8,
    &quot;failAmount&quot;: 1,
    &quot;successDetails&quot;: [
      {
        &quot;id&quot;: &quot;528989565877224448&quot;,
        &quot;name&quot;: &quot;tagWhite2&quot;,
        &quot;color&quot;: &quot;white&quot;
      },
      {
        &quot;id&quot;: &quot;528989565877289984&quot;,
        &quot;name&quot;: &quot;tagBlue&quot;,
        &quot;color&quot;: &quot;blue&quot;
      },
      {
        &quot;id&quot;: &quot;528989565877355520&quot;,
        &quot;name&quot;: &quot;tagGreen&quot;,
        &quot;color&quot;: &quot;green&quot;
      },
      {
        &quot;id&quot;: &quot;528989565894001664&quot;,
        &quot;name&quot;: &quot;tagYellow&quot;,
        &quot;color&quot;: &quot;yellow&quot;
      },
      {
        &quot;id&quot;: &quot;528989565894067200&quot;,
        &quot;name&quot;: &quot;tagPurple&quot;,
        &quot;color&quot;: &quot;purple&quot;
      },
      {
        &quot;id&quot;: &quot;528989565894132736&quot;,
        &quot;name&quot;: &quot;tagWhite&quot;,
        &quot;color&quot;: &quot;white&quot;
      },
      {
        &quot;id&quot;: &quot;528989565894198272&quot;,
        &quot;name&quot;: &quot;tagEmpty&quot;,
        &quot;color&quot;: &quot;white&quot;
      },
      {
        &quot;id&quot;: &quot;528989565910778880&quot;,
        &quot;name&quot;: &quot;tagRed&quot;,
        &quot;color&quot;: &quot;red&quot;
      }
    ],
    &quot;failDetails&quot;: [
      {
        &quot;code&quot;: 43023,
        &quot;name&quot;: &quot;tagInvalid&quot;,
        &quot;msg&quot;: &quot;tag color not found&quot;
      }
    ]
  }
}
```

## Response Data Description

| Parameter Name | Type               | Description          |
| -------------- | ------------------ | -------------------- |
| totalAmount    | integer            | Total requests       |
| successAmount  | integer            | Total successes      |
| failAmount     | integer            | Total failures       |
| successDetails | array[SuccessDetails] | Success details      |
| failDetails    | array[FailDetails]   | Failure details      |

### successDetails Success Info &lt;SuccessDetails&gt;

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| id             | string | Tag ID      |
| name           | string | Tag name    |
| color          | string | Tag color   |

### failDetails Failure Info &lt;FailDetails&gt;

| Parameter Name | Type    | Description |
| -------------- | ------- | ----------- |
| code           | integer | Error code  |
| name           | string  | Tag name    |
| msg            | string  | Error msg   |

## Error Codes

Below are the specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 43020      | Tag name is empty                  |
| 43021      | Tag name already exists            |
| 43023      | Tag color not supported, see color list |
