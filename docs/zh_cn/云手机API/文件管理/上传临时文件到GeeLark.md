[TOC]

# 一、获取上传文件的临时地址uploadUrl
## 接口说明

上传临时文件到GeeLark，文件有效期30天

## 请求URL

- `https://openapi.geelark.cn/open/v1/upload/getUrl`

## 请求方法

- POST

## 请求参数

| 参数名       | 必选   |     类型   |    说明    |示例|
| ----------- | -------| -----------|----------- |--------- |
| fileType   | 是     |   string | 文件类型, 目前支持：&quot;jpg&quot;, &quot;jpeg&quot;, &quot;png&quot;, &quot;gif&quot;, &quot;bmp&quot;, &quot;tiff&quot;, &quot;tif&quot;, &quot;webp&quot;, &quot;svg&quot;, &quot;heif&quot;, &quot;heic&quot;,&quot;mp4&quot;, &quot;avi&quot;, &quot;mkv&quot;, &quot;mov&quot;, &quot;wmv&quot;, &quot;flv&quot;, &quot;webm&quot;, &quot;mpeg&quot;, &quot;mpg&quot;, &quot;3gp&quot;,&quot;apk&quot;,&quot;xapk&quot;,&quot;xml&quot;,&quot;mp3&quot; | jpg |

## 请求示例

```json
{
    &quot;fileType&quot;: &quot;mp4&quot;
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
 &quot;traceId&quot;: &quot;9F49062C8DB3C90D8E94B4DFA37BDF89&quot;,
 &quot;code&quot;: 0,
 &quot;msg&quot;: &quot;success&quot;,
 &quot;data&quot;: {
 &quot;uploadUrl&quot;: &quot;http://42-studio-prod.oss-cn-hangzhou.aliyuncs.com/open-upload%2F497521349346987872%2F20240730%2Fe2u5amyB.txt?Expires=1722310832&amp;OSSAccessKeyId=LTAI5t7JzQBfi1nV3HbsKojG&amp;Signature=HGBVqTUfXcUAthLPnO3ZYIVnAxg%3D&quot;,
 &quot;resourceUrl&quot;: &quot;https://material-prod.geelark.cn/open-upload/497521349346987872/20240730/e2u5amyB.txt&quot;
 }
}
```

## 错误码

错误码请参考[云手机错误码](https://open.geelark.cn/api/cloud-phone-error-codes)

# 二、用uploadUrl上传文件(上传成功后可通过resourceUrl访问文件)
### 上传使用示例

## linux
``` shell
curl -X PUT --upload-file ./upload_test.txt &quot;uploadUrl&quot;
```

## Go
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
Ps：注意Header不能传多余的字段 ！
![](http://doc.geelark.cn/server/index.php?s=/api/attachment/visitFile&amp;sign=856e00cdf60895e5bd82eaafcc4a6e98)
![](http://doc.geelark.cn/server/index.php?s=/api/attachment/visitFile&amp;sign=1e0a8e05e4459b1f1efaa6060f58da9b)