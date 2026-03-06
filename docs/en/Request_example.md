[TOC]

## Example

```js
const url = "http://localhost:40185/api/v1/browser/start"; // Sample request address



var data = {
 "id": "123456789xxxx"
};

fetch(url, {
 method: "POST",
 headers: {
 "Content-Type": "application/json",
 },
 body: JSON.stringify(data),
})
 .then((res) => res.json())
 .then((res) => {
 console.log(res);
 })
 .catch((err) => {
 console.error(err);
 });
```