# 一、获取上传文件的临时地址uploadUrl
## 接口说明

上传临时文件到GeeLark，文件有效期3天

## 请求URL

- `https://openapi.geelark.cn/open/v1/upload/getUrl`

## 请求方法

- POST

## 请求参数

| 参数名       | 必选   |     类型   |    说明    |示例|
| ----------- | -------| -----------|----------- |--------- |
| fileType   | 是     |   string | 文件类型, 目前支持："jpg", "jpeg", "png", "gif", "bmp", "webp","heif", "heic", "mp4", "webm","xml", "apk", "xapk" | "jpg" |

## 请求示例

```json
{
    "fileType": "mp4"
}
```

## 响应体数据说明

| 参数名       |     类型   |    说明    |
| ----------- | -----------|----------- |
| uploadUrl | string   | 上传文件的url (有效期30分钟) |
| resourceUrl  | string    | 资源访问url |

## 响应示例

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

## 错误码

错误码请参考[云手机错误码](https://open.geelark.cn/api/cloud-phone-error-codes)

# 二、用uploadUrl上传文件(上传成功后可通过resourceUrl访问文件)
### 上传使用示例

## linux
``` shell
curl -X PUT --upload-file ./upload_test.mp4 "uploadUrl"
```

## Go
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
Ps：注意Header不能传多余的字段 ！
![](http://doc.geelark.cn/server/index.php?s=/api/attachment/visitFile&sign=856e00cdf60895e5bd82eaafcc4a6e98)
![](http://doc.geelark.cn/server/index.php?s=/api/attachment/visitFile&sign=1e0a8e05e4459b1f1efaa6060f58da9b)