## API Description

Create an automation task: Import custom task flow. Returns `taskId` in `data`.

## Request URL

* `https://openapi.geelark.com/open/v1/task/flow/import`

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
| id | no |string| custom task flow id, If the corresponding ID is passed, it will be updated; if not, a new one will be created |
| gal | no |string| custom task flow data |

## Request Example

```json
{
    "id": "612345671223083526",
    "gal" : "{\"content\":{\"contents\":[{\"config\":{\"packgename\":\"com.zhiliaoapp.musically\",\"remark\":\"\",\"timeout\":30000},\"type\":\"openApp\"},{\"config\":{\"remark\":\"\",\"timeout\":10000,\"timeoutMax\":300000,\"timeoutMin\":1000,\"timeoutType\":\"fixedValue\"},\"type\":\"waitTime\"},{\"config\":{\"filters\":[{\"content\":\"Home\",\"type\":\"text\"}],\"remark\":\"\",\"searchTime\":3000,\"serial\":1,\"serialMax\":50,\"serialMin\":1,\"serialType\":\"fixedValue\",\"variable\":\"\"},\"type\":\"click\"},{\"config\":{\"remark\":\"\",\"timeout\":2000,\"timeoutMax\":300000,\"timeoutMin\":1000,\"timeoutType\":\"fixedValue\"},\"type\":\"waitTime\"},{\"config\":{\"filters\":[{\"content\":\"For You\",\"type\":\"text\"},{\"content\":\"android:id/text1\",\"type\":\"id\"}],\"remark\":\"\",\"searchTime\":30,\"serial\":1,\"serialMax\":50,\"serialMin\":1,\"serialType\":\"fixedValue\",\"variable\":\"\"},\"type\":\"click\"},{\"config\":{\"remark\":\"\",\"timeout\":2000,\"timeoutMax\":300000,\"timeoutMin\":1000,\"timeoutType\":\"fixedValue\"},\"type\":\"waitTime\"},{\"config\":{\"direction\":\"top\",\"distanceMax\":700,\"distanceMin\":500,\"position\":[300,700],\"randomWheelSleepTime\":[300,500],\"remark\":\"\"},\"type\":\"scrollPage\"},{\"config\":{\"remark\":\"\",\"timeout\":2000,\"timeoutMax\":300000,\"timeoutMin\":1000,\"timeoutType\":\"fixedValue\"},\"type\":\"waitTime\"},{\"config\":{\"direction\":\"top\",\"distanceMax\":700,\"distanceMin\":500,\"position\":[300,700],\"randomWheelSleepTime\":[300,500],\"remark\":\"\"},\"type\":\"scrollPage\"},{\"config\":{\"remark\":\"\",\"timeout\":2000,\"timeoutMax\":300000,\"timeoutMin\":1000,\"timeoutType\":\"fixedValue\"},\"type\":\"waitTime\"},{\"config\":{\"children\":[{\"config\":{\"direction\":\"top\",\"distanceMax\":600,\"distanceMin\":500,\"position\":[300,700],\"randomWheelSleepTime\":[300,500],\"remark\":\"\"},\"type\":\"scrollPage\"},{\"config\":{\"filters\":[{\"content\":\"com.zhiliaoapp.musically:id/nl8\",\"type\":\"id\"}],\"remark\":\"\",\"searchTime\":30,\"serial\":1,\"serialMax\":50,\"serialMin\":1,\"serialType\":\"fixedValue\",\"variable\":\"avatar\"},\"type\":\"waitEle\"},{\"config\":{\"children\":[{\"config\":{\"remark\":\"\",\"timeout\":2000,\"timeoutMax\":30000,\"timeoutMin\":10000,\"timeoutType\":\"randomInterval\"},\"type\":\"waitTime\"},{\"config\":{\"children\":[{\"config\":{\"filters\":[{\"content\":\"com.zhiliaoapp.musically:id/cf6\",\"type\":\"id\"}],\"remark\":\"\",\"searchTime\":3000,\"serial\":1,\"serialMax\":50,\"serialMin\":1,\"serialType\":\"fixedValue\"},\"type\":\"click\"}],\"hiddenChildren\":false,\"other\":[],\"probability\":30,\"relation\":\"random\",\"remark\":\"\"},\"type\":\"ifElse\"},{\"config\":{\"remark\":\"\",\"timeout\":2000,\"timeoutMax\":30000,\"timeoutMin\":10000,\"timeoutType\":\"fixedValue\"},\"type\":\"waitTime\"}],\"condition\":[\"avatar\"],\"hiddenChildren\":false,\"other\":[],\"relation\":\"exist\",\"remark\":\"\"},\"type\":\"ifElse\"}],\"hiddenChildren\":false,\"remark\":\"\",\"times\":15,\"variableIndex\":\"for_times_index\"},\"type\":\"forTimes\"},{\"config\":{\"remark\":\"\",\"timeout\":120000,\"timeoutMax\":300000,\"timeoutMin\":1000,\"timeoutType\":\"fixedValue\"},\"type\":\"waitTime\"}],\"errorType\":\"skip\",\"isDebug\":false,\"timeOut\":\"30\",\"contentType\":\"phone\"},\"desc\":\"A TikTok Task flow\",\"title\":\"TikTok\"}"
}
```

## Response Example

```json
{
    "traceId": "A9D852F29EA2CA1BA46B963DB449329A",
    "code": 0,
    "msg": "success",
    "data": {
        "id": "612345671223083526" // custom task flow id
    }
}
```

## Error Codes

For error codes, please refer to [Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 48002 | custom task flow not found |

## Response Data Description

| Field | Type | Description |
| --- | --- | --- |
| traceId | string | Request identifier |
| code | integer | `0` = success |
| msg | string | Status message |
| data | object | Response payload (see example) |

## Error Codes

See [Cloud Phone Error Codes](../../../Error%20Codes/Cloud_Phone_Error_Codes.md). Interface-specific codes may also appear in the response `msg` / `code` fields.
