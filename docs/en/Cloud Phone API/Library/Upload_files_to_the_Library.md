#1. Get the Upload URL for Uploading a File to the Library

API Description
---------------

Upload a file to the Library, the file is valid for 30 days. Please add it to the Library immediately after successful upload, if the file not added, it will be deleted.

Request URL
-----------

- `https://openapi.geelark.com/open/v1/material/getUploadUrl`

Request Method
--------------

* POST

Request Parameters
------------------

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| fileType | Yes | string | File type, Currently supported: "jpg", "jpeg", "png", "gif", "bmp", "webp","heif", "heic", "mp4", "webm","xml", "apk", "xapk" | "jpg" |

Request Example
---------------


```json
{
    "fileType": "jpg"
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
    "traceId": "AC5B5C9ABF8BF925A504A8849A4862B2",
    "code": 0,
    "msg": "success",
    "data": {
        "uploadUrl": "http://42-studio-singapore.oss-ap-southeast-3.aliyuncs.com/open-material-upload%2F503609206784396150%2F20260309%2FVwujVZdl.jpg?Expires=1773046044&OSSAccessKeyId=LTAI5t7JzQBfi1nV3HbsKojG&Signature=TZbYGwfcad4XFiyh4mZ1gdVI%2FzI%3D",
        "resourceUrl": "https://singapore-upgrade.geelark.com/open-material-upload/503609206784396150/20260309/VwujVZdl.jpg"
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
curl -X PUT --upload-file ./upload_test.jpg "uploadUrl"
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
client := &http.Client{}
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
![](http://doc.geelark.com/server/index.php?s=/api/attachment/visitFile&sign=cce0a71903f159b1db961d12744344e7)
![](http://doc.geelark.com/server/index.php?s=/api/attachment/visitFile&sign=ae5829e137fe8c2860471990237fc020)