[TOC]

## Example

```js
const url = &quot;http://localhost:40185/api/v1/browser/start&quot;; // Sample request address



var data = {
 &quot;id&quot;: &quot;123456789xxxx&quot;
};

fetch(url, {
 method: &quot;POST&quot;,
 headers: {
 &quot;Content-Type&quot;: &quot;application/json&quot;,
 },
 body: JSON.stringify(data),
})
 .then((res) =&gt; res.json())
 .then((res) =&gt; {
 console.log(res);
 })
 .catch((err) =&gt; {
 console.error(err);
 });
```