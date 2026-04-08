## Example

```js
const url = "http://localhost:40185/api/v1/browser/start"; // Sample request address

const appToken = "your appToken";

var data = {
 "id": "123456789xxxx"
};

fetch(url, {
 method: "POST",
 headers: {
 "Content-Type": "application/json",
 "Authorization": "Bearer " + appToken,
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