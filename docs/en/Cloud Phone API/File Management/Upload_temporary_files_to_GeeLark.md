[TOC]

#1. Obtain a temporary upload URL &quot;uploadUrl&quot; for the file.

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
| fileType | Yes | string | File type, Currently supported: &quot;jpg&quot;, &quot;jpeg&quot;, &quot;png&quot;, &quot;gif&quot;, &quot;bmp&quot;, &quot;tiff&quot;, &quot;tif&quot;, &quot;webp&quot;, &quot;svg&quot;, &quot;heif&quot;, &quot;heic&quot;,&quot;mp4&quot;, &quot;avi&quot;, &quot;mkv&quot;, &quot;mov&quot;, &quot;wmv&quot;, &quot;flv&quot;, &quot;webm&quot;, &quot;mpeg&quot;, &quot;mpg&quot;, &quot;3gp&quot;,&quot;apk&quot;,&quot;xapk&quot;,&quot;xml&quot;,&quot;mp3&quot;| jpg |

Request Example
---------------


```json
{
    &quot;fileType&quot;: &quot;mp4&quot;
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
 &quot;traceId&quot;: &quot;9F49062C8DB3C90D8E94B4DFA37BDF89&quot;,
 &quot;code&quot;: 0,
 &quot;msg&quot;: &quot;success&quot;,
 &quot;data&quot;: {
 &quot;uploadUrl&quot;: &quot;http://42-studio-prod.oss-cn-hangzhou.aliyuncs.com/open-upload%2F497521349346987872%2F20240730%2Fe2u5amyB.txt?Expires=1722310832&amp;OSSAccessKeyId=LTAI5t7JzQBfi1nV3HbsKojG&amp;Signature=HGBVqTUfXcUAthLPnO3ZYIVnAxg%3D&quot;,
 &quot;resourceUrl&quot;: &quot;https://material-prod.geelark.cn/open-upload/497521349346987872/20240730/e2u5amyB.txt&quot;
 }
}
```

Error Codes
-----------

For error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes)

# 2.Upload the file using &quot;uploadUrl&quot; (after a successful upload, the file can be accessed via resourceUrl).

Upload Usage Example
-----------

### linux
``` shell
curl -X PUT --upload-file ./upload_test.txt &quot;uploadUrl&quot;
```

### Go
```go
// upload file path
filePath := &quot;/Users/xxx/Desktop/upload_test.mp4&quot;

// open file
file, err := os.Open(filePath)
if err != nil {
 fmt.Println(&quot;Error opening file:&quot;, err)
 return
}

// create http client
url := &quot;uploadUrl&quot;
req, err := http.NewRequest(&quot;PUT&quot;, url, file)
if err != nil {
 fmt.Println(&quot;Error creating request:&quot;, err)
 return
}

// send request
client := &amp;http.Client{}
resp, err := client.Do(req)
if err != nil {
 fmt.Println(&quot;Error sending request:&quot;, err)
 return
}
defer resp.Body.Close()

// handle response
if resp.StatusCode == http.StatusOK {
 fmt.Println(&quot;File uploaded successfully!&quot;)
} else {
 fmt.Println(&quot;Error uploading file:&quot;, resp.Status)
}
```
## Postman
Please note that the header cannot pass any extra fields!
![](http://doc.geelark.cn/server/index.php?s=/api/attachment/visitFile&amp;sign=55a9c6fd741b6c9b78e71e4beb948dd3)
![](http://doc.geelark.cn/server/index.php?s=/api/attachment/visitFile&amp;sign=e9ccd1ef2db200455f61ce465a989b20)