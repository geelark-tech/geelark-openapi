## API Description

API: Upload files to the Library.

## Request URL

* `https://openapi.geelark.com/open/v1/material/getUploadUrl`

## Request Method

* POST

## Authentication

All requests are `POST` with `Content-Type: application/json`.

Required headers:

- `traceId`: Version 4 UUID (uppercase recommended)
- **Token mode:** `Authorization: Bearer YOUR_API_TOKEN`
- **Key mode:** `appId`, `traceId`, `ts`, `nonce`, `sign` (see [Request Instructions](../../User%20Guide/Cloud%20Phone/Request_Instructions.md))

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| fileType | Yes | string | File type, Currently supported: "jpg", "jpeg", "png", "gif", "bmp", "webp","heif", "heic", "mp4", "webm","xml", "apk", "xapk" | "jpg" |

## Request Example

```json
{
    "fileType": "jpg"
}
```

## Response Example

```json
{
    "traceId": "AC5B5C9ABF8BF925A504A8849A4862B2",
    "code": 0,
    "msg": "success",
    "data": {
        "uploadUrl": "http://42-studio-singapore.oss-ap-southeast-3.aliyuncs.com/open-material-upload%2F503609206784396150%2F20260309%2FVwujVZdl.jpg?Expires=1773046044&OSSAccessKeyId=LTAI5t7JzQBfi1nV3HbsKojG&Signature=TZbYGwfcad4XFiyh4mZ1gdVI%2FzI%3D",
        "resourceUrl": "https://singapore-upgrade.geelark.com/open-material-upload/503609206784396150/20260309/VwujVZdl.jpg"
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

## Error Codes

See [Cloud Phone Error Codes](../../Error%20Codes/Cloud_Phone_Error_Codes.md). Interface-specific codes may also appear in the response `msg` / `code` fields.
