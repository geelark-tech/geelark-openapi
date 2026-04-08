## API Description


Querying browser bookmark settings does not require sending a request body.



## Request URL


- `http://localhost:40185/api/v1/browser/getBookmark`


## Request Method


- POST


## Response body data description


| Parameter Name | Type | Description |
| --- | --- | --- |
| browserBookmark | BrowserBookmark | Browser Bookmarks |


### BrowserBookmark


| Parameter Name | Type | Description |
| --- | --- | --- |
|type|integer|Bookmark type, 0 - No setting, 1 - Uploaded file, 2 - Manually created|
|fileAddr|string|Bookmark HTML file address|
|text|string|Manually created bookmark content, multiple bookmarks separated by newline characters \n, supported formats:</br>Folder::Name::URL</br>Name::URL</br>URL|



## Response Example



```json
{
    "traceId":"123456ABCDEF",
    "code":0,
    "msg":"success",
    "data":{
        "browserBookmark":{
            "type":2,
            "fileAddr":"",
            "text":"http://a.com\nhttp://b.com"
        }
    }
}
```