[TOC]

# Request Example

## Token verification

```js
const url = &quot;https://openapi.geelark.com/open/v1/phone/list&quot;;

const appToken = &quot;your appToken&quot;;

var traceUUid = &quot;yxxyxxxxyxyxxyxxyxxxyxxxyxxyxxyx&quot;.replace(
 /[xy]/g,
 function (c) {
 var r = (Math.random() * 16) | 0, 
 v = c == &quot;x&quot; ? r : (r &amp; 0x3) | 0x8; 
 return v.toString(16); 
 }
);

var traceId = traceUUid.toUpperCase();

var data = {
 page: 1,
 pageSize: 10,
 tags: [&quot;tagNew&quot;],
};

fetch(url, {
 method: &quot;POST&quot;,
 headers: {
 &quot;Content-Type&quot;: &quot;application/json&quot;,
 traceId: traceId,
 Authorization: &quot;Bearer &quot; + appToken,
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

## Key verification

```js
const CryptoJS = require(&quot;crypto-js&quot;);

const url = &quot;https://openapi.geelark.com/open/v1/phone/list&quot;; // Example request URL

const appID = &quot;your appID&quot;; // Your appID
const apiKey = &quot;your apiKey&quot;; // Your apiKey

let timestamp = new Date().getTime().toString(); // Millisecond timestamp

// Generate UUID
var traceUUid = &quot;yxxyxxxxyxyxxyxxyxxxyxxxyxxyxxyx&quot;.replace(
 /[xy]/g,
 function (c) {
 var r = (Math.random() * 16) | 0, // Randomly generate a number between 0 and 15
 v = c == &quot;x&quot; ? r : (r &amp; 0x3) | 0x8; // If c is &#039;y&#039;, only take one of 8, 9, a, b
 return v.toString(16); // Convert the number to a hexadecimal string
 }
);

var traceId = traceUUid.toUpperCase();

// nonce is the first 6 characters of traceId
var nonce = traceId.substring(0, 6);

var sign = CryptoJS.SHA256(appID + traceId + timestamp + nonce + apiKey)
 .toString()
 .toUpperCase();

var data = {
 page: 1,
 pageSize: 10,
};

headers = {
 &quot;Content-Type&quot;: &quot;application/json&quot;,
 appId: appID,
 traceId: traceId,
 ts: timestamp,
 nonce: nonce,
 sign: sign,
};

console.log(headers);

fetch(url, {
 method: &quot;POST&quot;,
 headers: {
 &quot;Content-Type&quot;: &quot;application/json&quot;,
 appId: appID,
 traceId: traceId,
 ts: timestamp,
 nonce: nonce,
 sign: sign,
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
