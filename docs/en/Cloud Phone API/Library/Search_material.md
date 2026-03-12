## Interface Description
search material


## Request URL

- `https://openapi.geelark.com/open/v1/material/search`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type          | Description           | Example           |
| --- | --- | --- | --- | --- |
| page | No | int | page | Refer to Request Example  |
| pageSize | No | int | page size （max: 200） | Refer to Request Example  |
| fileName | No | string | search file name | Refer to Request Example  |
| tagsId | No | array[string] |search tag id | Refer to Request Example  |
| source | No | int | source: 0-upload，1-AI Edit 2Baidu  Cloud Drive 3GhostCut 4GoogleDrive 5Image to video | Refer to Request Example  |
| fileType | No | array[int] | file type  1-image，2-video | Refer to Request Example  |
| ids | No | array[string] |ID array，The maximum length of the array is 100. | ["5213214343124321"] |


## Request Example
```json
{
    "fileType" : [1],
    "fileName" : "demo",
    "tagIds" : ["569577514586891738"],
    "source" : 1,
    "page" : 1,
    "pageSize" : 50,
	"ids": ["608127302118696420"] 
}
```


## Response Example

```json
{
    "traceId": "8D192F0785AEAAFA879FA44A990BEDAC",
    "code": 0,
    "msg": "success",
    "data": {
        "total": 12,
        "page": 1,
        "pageSize": 50,
        "list": [
            {
                "id": "569546671000653787",
                "createdTime": 1749005870,
                "fileName": "2025_06_02_11_31_IMG_9607.MOV",
                "fileSize": 120713028,
                "fileUrl": "https://material.geelark.cn/user-upload/497521349346987872/material-center/Ryzt3vkK14T5asJQPx2W.MOV",
                "fileType": 2,
                "width": 2160,
                "height": 3840,
                "source": 0,
                "tags": [
                    {
                        "id": "569577514586891738",
                        "name": "2",
                        "color": 2
                    }
                ],
                "userName": "Tom"
            }
        ]
    }
}
```

## Response Data Description

| Parameter Name | Type              | Description          |
| ----------- | -----------|----------- 
| total | int | total data |
| page | int |current page  |
| pageSize | int | current page size  |
| list | array[MaterialData] | material data |

## MaterialData Data Description

| Parameter Name | Type              | Description          |
| ----------- | -----------|----------- 
| id | int | material id |
| createdTime | int | Creation time, second level timestamp |
| fileName | string | material name |
| fileSize | int | material file size,  byte |
| fileUrl | string | material url |
| fileType | int | material file type   1-image，2-video |
| width | int | width |
| height | int | height |
| source | int | source: 0-upload，1-AI Edit 2Baidu  Cloud Drive 3GhostCut 4GoogleDrive 5Image to video |
| tags | array[TagData] | tag data |
| userName | string | upload user name |

## TagData Data Description

| Parameter Name | Type              | Description          |
| ----------- | -----------|----------- |
| id | int | tag id |
| name | int |tag id  |
| color | int | tag color: 0 White 1 Red 2 Blue 3 Green 4 Yellow 5 Purple |

## Error Codes

Below are specific error codes for the API. For other error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).