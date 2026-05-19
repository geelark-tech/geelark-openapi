## API Description

Create an automation task: Instagram publish Reels video. Returns `taskId` in `data`.

## Request URL

* `https://openapi.geelark.com/open/v1/rpa/task/instagramPubReels`

## Request Method

* POST

## Authentication

All requests are `POST` with `Content-Type: application/json`.

Required headers:

- `traceId`: Version 4 UUID (uppercase recommended)
- **Token mode:** `Authorization: Bearer YOUR_API_TOKEN`
- **Key mode:** `appId`, `traceId`, `ts`, `nonce`, `sign` (see [Request Instructions](../../../User%20Guide/Cloud%20Phone/Request_Instructions.md))

## Request Parameters

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| name | No | string | Task name, up to 128 characters |
| remark | No | string | Remarks, up to 200 characters |
| scheduleAt | Yes | integer | Scheduled time (timestamp) |
| id | Yes | string | Cloud phone ID |
| description | Yes | string | Caption, up to 2200 characters |
| video | Yes | \[\]string | Videos, up to 10, to upload videos, please refer to [Upload Temporary Files to GeeLark](https://open.geelark.com/api/upload-getUrl)|
| sameStyleUrl | No | string | Same URL |
| sameStyleVoice | No | integer | Same volume, range 0-100 |
| originalVoice | No | integer | Original volume, range 0-100 |
| aiTag | No | bool | AI tag, defaults to false. |
| needShareLink | No | bool | Whether to retrieve the sharing link, the default is false. |

## Request Example

```json
{
 "name":"test",
 "remark":"test remark",
 "scheduleAt": 1741846843,
 "id":"557536075321468390",
 "description":"description",
 "video": ["https://material.geelark.com/a.mp4"]
}
```

## Response Example

```json
{
    "traceId": "A4D8BCF69B878A71AC589F5CB1D80EAB",
    "code": 0,
    "msg": "success",
    "data": {
        "taskId": "558017255909123564"
    }
}
```

## Response Data Description

| Field | Type | Description |
| --- | --- | --- |
| traceId | string | Request identifier |
| code | integer | `0` = success |
| msg | string | Status message |
| data | object | Response payload (see example) |

### `data` fields (typical for automation tasks)

| Field | Type | Description |
| --- | --- | --- |
| taskId | string | Task ID — see Related APIs below; optional Webhook callback type `6` |

## Related APIs

- [Query task](../Task%20Management/Query_task.md)
- [Task Detail](../Task%20Management/Task_Detail.md)
- [Cancel task](../Task%20Management/Cancel_task.md)

## Error Codes

See [Cloud Phone Error Codes](../../../Error%20Codes/Cloud_Phone_Error_Codes.md). Interface-specific codes may also appear in the response `msg` / `code` fields.
