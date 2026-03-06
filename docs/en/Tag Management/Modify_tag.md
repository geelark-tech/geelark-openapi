[TOC]


## Interface Description

- Modify tag information including name and color.

**Refer to the Create Tag API for the list of tag colors.**

## Request URL

- `https://openapi.geelark.com/open/v1/tag/update`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type       | Description           | Example           |
| -------------- | -------- | ---------- | --------------------- | ----------------- |
| list           | Yes      | array[Tag] | Array of tags to update | Refer to Request Example |

### list Modify Tag Array &lt;Tag&gt;

| Parameter Name | Required | Type   | Description | Example           |
| -------------- | -------- | ------ | ----------- | ----------------- |
| id             | Yes      | string | Tag ID      | Refer to Request Example |
| name           | No       | string | New tag name, up to 30 characters| Refer to Request Example |
| color          | No       | string | New tag color| Refer to Request Example |

- If the tag information includes a name, it cannot be an empty string.

## Request Example

```json
{
  &quot;list&quot;: [
    {
      &quot;id&quot;: &quot;528989565894198272&quot;,
      &quot;name&quot;: &quot;tagEmptyUpdate&quot;,
      &quot;color&quot;: &quot;red&quot;
    },
    {
      &quot;id&quot;: &quot;528994200482481152&quot;,
      &quot;name&quot;: &quot;tagUpdate&quot;,
      &quot;color&quot;: &quot;red&quot;
    }
  ]
}
```

## Response Example

```json
{
  &quot;traceId&quot;: &quot;B178151A9586E88195C4BF1493BBC98B&quot;,
  &quot;code&quot;: 0,
  &quot;msg&quot;: &quot;success&quot;,
  &quot;data&quot;: {
    &quot;totalAmount&quot;: 2,
    &quot;successAmount&quot;: 2,
    &quot;failAmount&quot;: 0
  }
}
```

## Error Codes

Below are the specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 43020      | Tag name is empty                  |
| 43022      | Tag does not exist                 |
| 43023      | Tag color not supported            |

