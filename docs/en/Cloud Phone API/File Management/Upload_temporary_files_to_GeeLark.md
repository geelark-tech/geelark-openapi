## API Description

API: Upload temporary files to GeeLark.

## Request URL

* `https://openapi.geelark.com/open/v1/upload/getUrl`

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
| fileType | Yes | string | File type, Currently supported: "jpg", "jpeg", "png", "gif", "bmp", "webp","heif", "heic", "mp4", "webm","xml", "apk", "xapk" |"mp4"|

## Request Example

```json
{
    "fileType": "mp4"
}
```

## Response Example

```json
{
 "traceId": "9F49062C8DB3C90D8E94B4DFA37BDF89",
 "code": 0,
 "msg": "success",
 "data": {
 "uploadUrl": "http://42-studio-prod.oss-cn-hangzhou.aliyuncs.com/open-upload%2F497521349346987872%2F20240730%2Fe2u5amyB.mp4?Expires=1722310832&OSSAccessKeyId=LTAI5t7JzQBfi1nV3HbsKojG&Signature=HGBVqTUfXcUAthLPnO3ZYIVnAxg%3D",
 "resourceUrl": "https://material-prod.geelark.cn/open-upload/497521349346987872/20240730/e2u5amyB.mp4"
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
