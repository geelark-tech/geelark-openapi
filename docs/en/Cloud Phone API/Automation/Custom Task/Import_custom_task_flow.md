API Description
-----------
Import or update custom task flow

Request URL
-----------

* `https://openapi.geelark.com/open/v1/task/flow/import`

Request Method
--------------

* POST

Request Parameters
------------------

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| id | no |string| custom task flow id, If the corresponding ID is passed, it will be updated; if not, a new one will be created |
| gal | no |string| custom task flow data |

Request Example
----------------

```json
{
    "id": "612345671223083526",
    "gal" : "{\"content\":{\"contents\":[{\"config\":{\"packgename\":\"com.zhiliaoapp.musically\",\"remark\":\"\",\"timeout\":30000},\"type\":\"openApp\"},{\"config\":{\"remark\":\"\",\"timeout\":10000,\"timeoutMax\":300000,\"timeoutMin\":1000,\"timeoutType\":\"fixedValue\"},\"type\":\"waitTime\"},{\"config\":{\"filters\":[{\"content\":\"Home\",\"type\":\"text\"}],\"remark\":\"\",\"searchTime\":3000,\"serial\":1,\"serialMax\":50,\"serialMin\":1,\"serialType\":\"fixedValue\",\"variable\":\"\"},\"type\":\"click\"},{\"config\":{\"remark\":\"\",\"timeout\":2000,\"timeoutMax\":300000,\"timeoutMin\":1000,\"timeoutType\":\"fixedValue\"},\"type\":\"waitTime\"},{\"config\":{\"filters\":[{\"content\":\"For You\",\"type\":\"text\"},{\"content\":\"android:id/text1\",\"type\":\"id\"}],\"remark\":\"\",\"searchTime\":30,\"serial\":1,\"serialMax\":50,\"serialMin\":1,\"serialType\":\"fixedValue\",\"variable\":\"\"},\"type\":\"click\"},{\"config\":{\"remark\":\"\",\"timeout\":2000,\"timeoutMax\":300000,\"timeoutMin\":1000,\"timeoutType\":\"fixedValue\"},\"type\":\"waitTime\"},{\"config\":{\"direction\":\"top\",\"distanceMax\":700,\"distanceMin\":500,\"position\":[300,700],\"randomWheelSleepTime\":[300,500],\"remark\":\"\"},\"type\":\"scrollPage\"},{\"config\":{\"remark\":\"\",\"timeout\":2000,\"timeoutMax\":300000,\"timeoutMin\":1000,\"timeoutType\":\"fixedValue\"},\"type\":\"waitTime\"},{\"config\":{\"direction\":\"top\",\"distanceMax\":700,\"distanceMin\":500,\"position\":[300,700],\"randomWheelSleepTime\":[300,500],\"remark\":\"\"},\"type\":\"scrollPage\"},{\"config\":{\"remark\":\"\",\"timeout\":2000,\"timeoutMax\":300000,\"timeoutMin\":1000,\"timeoutType\":\"fixedValue\"},\"type\":\"waitTime\"},{\"config\":{\"children\":[{\"config\":{\"direction\":\"top\",\"distanceMax\":600,\"distanceMin\":500,\"position\":[300,700],\"randomWheelSleepTime\":[300,500],\"remark\":\"\"},\"type\":\"scrollPage\"},{\"config\":{\"filters\":[{\"content\":\"com.zhiliaoapp.musically:id/nl8\",\"type\":\"id\"}],\"remark\":\"\",\"searchTime\":30,\"serial\":1,\"serialMax\":50,\"serialMin\":1,\"serialType\":\"fixedValue\",\"variable\":\"avatar\"},\"type\":\"waitEle\"},{\"config\":{\"children\":[{\"config\":{\"remark\":\"\",\"timeout\":2000,\"timeoutMax\":30000,\"timeoutMin\":10000,\"timeoutType\":\"randomInterval\"},\"type\":\"waitTime\"},{\"config\":{\"children\":[{\"config\":{\"filters\":[{\"content\":\"com.zhiliaoapp.musically:id/cf6\",\"type\":\"id\"}],\"remark\":\"\",\"searchTime\":3000,\"serial\":1,\"serialMax\":50,\"serialMin\":1,\"serialType\":\"fixedValue\"},\"type\":\"click\"}],\"hiddenChildren\":false,\"other\":[],\"probability\":30,\"relation\":\"random\",\"remark\":\"\"},\"type\":\"ifElse\"},{\"config\":{\"remark\":\"\",\"timeout\":2000,\"timeoutMax\":30000,\"timeoutMin\":10000,\"timeoutType\":\"fixedValue\"},\"type\":\"waitTime\"}],\"condition\":[\"avatar\"],\"hiddenChildren\":false,\"other\":[],\"relation\":\"exist\",\"remark\":\"\"},\"type\":\"ifElse\"}],\"hiddenChildren\":false,\"remark\":\"\",\"times\":15,\"variableIndex\":\"for_times_index\"},\"type\":\"forTimes\"},{\"config\":{\"remark\":\"\",\"timeout\":120000,\"timeoutMax\":300000,\"timeoutMin\":1000,\"timeoutType\":\"fixedValue\"},\"type\":\"waitTime\"}],\"errorType\":\"skip\",\"isDebug\":false,\"timeOut\":\"30\",\"contentType\":\"phone\"},\"desc\":\"A TikTok Task flow\",\"title\":\"TikTok\"}"
}
```


Response Example
----------------

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