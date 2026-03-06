#1. Obtain a temporary upload URL "uploadUrl" for the file.

API Description
---------------

Upload temporary files to GeeLark (Expires in 30 days)

Request URL
-----------

* `https://openapi.geelark.com/open/v1/upload/getUrl`

Request Method
--------------

* POST

Request Parameters
------------------

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| fileType | Yes | string | File type, Currently supported: "jpg", "jpeg", "png", "gif", "bmp", "tiff", "tif", "webp", "svg", "heif", "heic","mp4", "avi", "mkv", "mov", "wmv", "flv", "webm", "mpeg", "mpg", "3gp","apk","xapk","xml","mp3"| jpg |

Request Example
---------------


```json
{
    "fileType": "mp4"
}
```

Response Data Description
-------------------------

| Parameter Name | Type | Description |
| --- | --- | --- |
| uploadUrl | string | URL for uploading the file (valid for 30 minutes) |
| resourceUrl | string | URL to access the resource |

Response Example
----------------

```json
{
 "traceId": "9F49062C8DB3C90D8E94B4DFA37BDF89",
 "code": 0,
 "msg": "success",
 "data": {
 "uploadUrl": "http://42-studio-prod.oss-cn-hangzhou.aliyuncs.com/open-upload%2F497521349346987872%2F20240730%2Fe2u5amyB.txt?Expires=1722310832&amp;OSSAccessKeyId=LTAI5t7JzQBfi1nV3HbsKojG&amp;Signature=HGBVqTUfXcUAthLPnO3ZYIVnAxg%3D",
 "resourceUrl": "https://material-prod.geelark.cn/open-upload/497521349346987872/20240730/e2u5amyB.txt"
 }
}
```

Error Codes
-----------

For error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes)

# 2.Upload the file using "uploadUrl" (after a successful upload, the file can be accessed via resourceUrl).

Upload Usage Example
-----------

### linux
``` shell
curl -X PUT --upload-file ./upload_test.txt "uploadUrl"
```

### Go
```go
// upload file path
filePath := "/Users/xxx/Desktop/upload_test.mp4"

// open file
file, err := os.Open(filePath)
if err != nil {
 fmt.Println("Error opening file:", err)
 return
}

// create http client
url := "uploadUrl"
req, err := http.NewRequest("PUT", url, file)
if err != nil {
 fmt.Println("Error creating request:", err)
 return
}

// send request
client := &amp;http.Client{}
resp, err := client.Do(req)
if err != nil {
 fmt.Println("Error sending request:", err)
 return
}
defer resp.Body.Close()

// handle response
if resp.StatusCode == http.StatusOK {
 fmt.Println("File uploaded successfully!")
} else {
 fmt.Println("Error uploading file:", resp.Status)
}
```
## Postman
Please note that the header cannot pass any extra fields!
![](http://doc.geelark.cn/server/index.php?s=/api/attachment/visitFile&amp;sign=55a9c6fd741b6c9b78e71e4beb948dd3)
![](http://doc.geelark.cn/server/index.php?s=/api/attachment/visitFile&amp;sign=e9ccd1ef2db200455f61ce465a989b20)