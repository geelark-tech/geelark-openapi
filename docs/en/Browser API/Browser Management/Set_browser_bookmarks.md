## API Description


Set browser bookmarks, and the bookmarks will be applied automatically when the browser environment starts.



## Request URL


- `http://localhost:40185/api/v1/browser/setBookmark`


## Request Method


- POST


## Request Parameters



| Parameter | Required | Type | Example | Description
| --- | --- | --- | --- | --- |
| browserBookmark | Yes | BrowserBookmark | Reference Request Example | Browser Bookmark |


### BrowserBookmark


| Parameter | Required | Type | Example | Description
| --- | --- | --- | --- | --- |
|type|Yes|integer|2|Bookmark type, 0-Not set, 1-Upload file, 2-Manually create|
|fileAddr|No|string|https://storage.com/bookmark.html|Bookmark HTML file address|
|text|No|string|Refer to request example|Manually create bookmark content, multiple bookmarks are separated by newline characters \n, supported formats:</br>Folder::Name::URL</br>Name::URL</br>URL|



## Request Example



```json
{
    "browserBookmark": {
        "type": 2,
        "fileAddr": "",
        "text": "http://a.com\nhttp://b.com"
    }
}
```



## Response Example



```json
{
    "traceId": "123456ABCDEF",
    "code": 0,
    "msg": "success"
}
```