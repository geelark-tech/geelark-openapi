API Description
---------------
* Currently, ADB only supports Android 9,11,12,13 ,14, 15 devices.
* Before set ADB status. Please start the cloud phone first.
* Enabling ADB is an asynchronous operation. It is recommended to wait about 3 seconds after enabling ADB before retrieving port, password, and other information.

Request URL
-----------

* `https://openapi.geelark.com/open/v1/adb/setStatus`

Request Method
--------------

* POST

Request Parameters
------------------

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| ids | Yes | array\[string\] | Array of cloud phone environment IDs (currently supports Android 11,12,13,14,15 ; unsupported models will be automatically filtered) | Refer to request example |
| open | Yes | bool | Open/Close | false |

## Request Example

```json
{
 	"ids" : [
		 "526209711930868736"
	 ],
 	"open" : true
}
```


## Response Example

```json
{
 "traceId": "A24A3089958A4BC28E8B89B3AE1A61AC",
 "code": 0,
 "msg": "success"
}
```

Error Codes
-----------

For error codes, please refer to  [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes)