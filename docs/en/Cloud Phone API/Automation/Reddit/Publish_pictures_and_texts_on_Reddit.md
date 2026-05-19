## API Description

Create an automation task: Publish pictures and texts on Reddit. Returns `taskId` in `data`.

## Request URL

* `https://openapi.geelark.com/open/v1/rpa/task/redditImage`

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
| title | Yes |string|Title|
| description | No |string|Description |
| images | Yes | \[\]string | Images, to upload images, please refer to [Upload Temporary Files to GeeLark](https://open.geelark.com/api/upload-getUrl)|
| community | Yes |string|Community |

## Request Example

```json
{
 "name":"test",
 "remark":"test remark",
 "scheduleAt": 1741846843,
 "id":"557536075321468390",
 "title": "title",
 "description":"description",
 "images": ["https://material.geelark.com/a.jpg"],
 "community": "cat"
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
