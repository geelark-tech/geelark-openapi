\[TOC\]

API Description
---------------

Move Group

Request URL
-----------

*   `https://openapi.geelark.com/open/v1/phone/moveGroup`
    

Request Method
--------------

*   POST
    

Request Parameters
------------------

| Parameter | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| envIds | Yes | array\[string\] | Array of cloud phone IDs, supports up to 100 elements | See request example |
| groupId | Yes | string | Group ID. Pass `&quot;0&quot;` to move to the ungrouped category | See request example |

Request Example
---------------
```json
{
    &quot;envIds&quot;: [
        &quot;601876382020062634&quot;
    ],
    &quot;groupId&quot;: &quot;590711571886417453&quot;
}
```
Response Example
----------------
```json
{
    &quot;traceId&quot;: &quot;B3DAFF64A7BD493CB1169D94A22BFC8D&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;
}
```
