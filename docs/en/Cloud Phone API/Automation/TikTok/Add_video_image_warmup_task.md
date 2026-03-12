## API Description

* Create a warmup task by directly calling the add task interface.
* To create video or image set tasks, you need to upload the materials first, then call the add task interface.
* The warmup task created by calling this interface is not automatically retried.

## Request URL

* `https://openapi.geelark.com/open/v1/task/add`

## Request Method

* POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| planName | No | string | Task plan name, auto-generated if not provided | testAdd |
| remark | No | string | Remarks, up to 200 characters | task |
| taskType | Yes | integer | Task type<br>1 Publish video<br>2 Warmup<br>3 Publish image set | 3 |
| list | Yes | array | Task parameter array, create a maximum of 100 tasks at a time | Refer to request examples |

### Publish Video Task Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| scheduleAt | Yes | integer | Scheduled time, in seconds timestamp. If the value is less than the current time, the value is calculated based on the current time. | 1718744459 |
| envId | Yes | string | Cloud phone ID | 123456654321 |
| video | Yes | string | Video URL | https://demo.geelark.com/open-upload/DhRP36s3.mp4 , to upload videos, please refer to [Upload Temporary Files to GeeLark](https://open.geelark.com/api/upload-getUrl) |
| videoDesc | No | string | Video description. Maximum 4000 characters | This is a video |
| productId | No | string | product id | 7498614361651,How to get the product ID: https://help.geelark.com/video-id-product-id|
| productTitle | No | string | Product display title | Title |
| refVideoId | No | string | Similar video ID | 722856939 ,How to get the video ID: https://help.geelark.com/video-id-product-id |
| maxTryTimes | No | integer | Maximum number of automatic retries. The value ranges from 0 to 3. The default value is 3 | 1 |
| timeoutMin | No | integer | Time-out period. The value ranges from 30 to 80 (unit minute). The default value is 80 | 30 |
| sameVideoVolume | No | integer | Same video volume, 0-100 | 30 |
| sourceVideoVolume | No | integer | Original video volume, 0-100 | 30 |
| markAI | No | bool | Whether to label AI generated content, default is false | false |
| cover | No | string | Video cover | https://demo.geelark.com/open-upload/DhRP36s3.jpg , to upload images, please refer to [Upload Temporary Files to GeeLark](https://open.geelark.com/api/upload-getUrl) |
| needShareLink | No | bool | Whether to obtain the sharing link, the default value is false | false |

### Warmup Task Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| scheduleAt | Yes | integer | Scheduled time, in seconds timestamp. If the value is less than the current time, the value is calculated based on the current time. | 1718744459 |
| envId | Yes | string | Cloud phone ID | 123456654321 |
| action | Yes | string | Warmup action<br>search profile - Search personal profile<br>search video - Search short videos<br>browse video - Randomly browse videos | browse video |
| keywords | No | array[string] | Search keyword, required when searching behavior, optional when browsing behavior | Refer to request examples |
| duration | Yes | integer | Browsing duration, in minutes | 10 |

### Publish Image Set Task Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| scheduleAt | Yes | integer | Scheduled time, in seconds timestamp. If the value is less than the current time, the value is calculated based on the current time. | 1718744459 |
| envId | Yes | string | Cloud phone ID | 123456654321 |
| images | Yes | array | Image URLs | Refer to request examples , to upload images, please refer to [Upload Temporary Files to GeeLark](https://open.geelark.com/api/upload-getUrl)|
| videoDesc | No | string | Video description. Maximum 4000 characters | This is an image set video |
| videoId | No | string | Same video ID | 722856939 ,How to get the video ID: https://help.geelark.com/video-id-product-id|
| videoTitle | No | string | Gallery Title. Maximum 90 characters | This is a gallery title |
| maxTryTimes | No | integer | Maximum number of automatic retries. The value ranges from 0 to 3. The default value is 3 | 1 |
| timeoutMin | No | integer | Time-out period. The value ranges from 30 to 80 (unit minute). The default value is 80 | 30 |
| sameVideoVolume | No | integer | Same video volume, 0-100 | 30 |
| markAI | No | bool | Whether to label AI generated content, default is false | false |
| needShareLink | No | bool | Whether to obtain the sharing link, the default value is false | false |

## Request Examples

### Example 1: Warmup


```json
{
    "planName": "testAdd",
    "taskType": 2,
    "list": [
        {
            "scheduleAt": 1718744459,
            "envId": "123456654321",
            "action": "search video",
            "keywords": ["hi"],
			"duration": 10
        }
    ]
}
```

### Example 2: Publish Video

```json
{
    "planName": "testAdd",
    "taskType": 1,
    "list": [
        {
            "scheduleAt": 1718744459,
            "envId": "123456654321",
            "video": "https://demo.geelark.com/open-upload/DhRP36s3.mp4"
        }
    ]
}
```

### Example 3: Publish Image Set

```json
{
    "planName": "testAdd",
    "taskType": 3,
    "list": [
        {
            "scheduleAt": 1718744459,
            "envId": "123456654321",
            "images": ["https://demo.geelark.com/open-upload/DhRP36s3.jpg", "https://demo.geelark.com/open-upload/DhRP36s3.jpg"]
        }
    ]
}
```

## Response Data Description

| Parameter Name | Type | Description |
| --- | --- | --- |
| taskIds | array | Array of task IDs |

## Response Example

```json
{
    "traceId": "123456ABCEDF",
    "code": 0,
    "msg": "success",
	"data": {
		"taskIds": [
			"123456ABCEDF"
		]
	}
}
```
## Error Codes

The following are specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| --- | --- |
| 41000 | Insufficient task credits |
| 43004 | Cloud phone has expired, please renew or upgrade your plan |
| 41001 | balance not enough |
| 43018 | The monthly cloud mobile phone is not bound to the monthly device |
| 48004 | The app required by the task does not meet the requirements |