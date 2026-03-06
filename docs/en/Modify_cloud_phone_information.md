
## Interface Description

###  Warning: Do not operate this api while calling the API to start the cloud phone.

- Modify cloud phone information.
- Support modifying the cloud phone name.
- Support modifying the cloud phone remark.
- Support modifying the cloud phone tags.
- Support modifying the cloud phone proxy configuration.
- Support modifying the cloud phone group.
- Support modifying the cloud phone charge mode.
- Support modifying the cloud phone number ( It needs to be in a shutdown state)

## Request URL

- `https://openapi.geelark.com/open/v1/phone/detail/update`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| -------------- | -------- | ------------- | ------------------------- | ------- |
| id | Yes | string | Cloud phone ID | |
| name | No | string | New cloud phone name, up to 100 characters | |
| remark | No | string | New cloud phone remark, up to 1500 characters | |
| groupID | No | string | New cloud phone group ID | |
| tagIDs | No | array[string] | New cloud phone tag IDs | |
| proxyConfig | No | Proxy | New cloud phone proxy config | |
| proxyId | No | string | Proxy Id | |
| phoneNumber | No | string | custom phone number | |

### proxyConfig Static Proxy Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| typeId | Yes | integer | Proxy type ID | 1 |
| server | Yes | string | Proxy server hostname | server.com |
| port | Yes | integer | Proxy server port | 1234 |
| username | Yes | string | Proxy server username | user |
| password | Yes | string | Proxy server password | password |

### proxyConfig Dynamic Proxy Parameters

Dynamic proxy settings can be configured on the client side first, and then by setting useProxyCfg to true, you can use the already configured information without needing to provide the host, port, and other details again.

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| useProxyCfg | Yes | bool | Whether to use the already configured proxy | true |
| typeId | Yes | integer | Proxy type ID | 20 |
| protocol | No | integer | Proxy protocol type: 1 for SOCKS5, 2 for HTTP. | 1 |
| server | No | string | Proxy server hostname | server.com |
| port | No | integer | Proxy server port | 1234 |
| username | No | string | Proxy server username | user |
| password | No | string | Proxy server password | password |
| country | No | string | country, Please refer to [the list of dynamic proxy country codes for possible values.](https://singapore-upgrade.geelark.com/apiResource/proxy-country.txt) | us |
| region | No | string | region, Please refer to the corresponding proxy: [Country Codes](https://singapore-upgrade.geelark.com/apiResource/proxies-country-codes.txt) | Please fill it out based on the proxy you’re using |
| city | No | string | city, Please refer to the corresponding proxy: [Country Codes](https://singapore-upgrade.geelark.com/apiResource/proxies-country-codes.txt) | Please fill it out based on the proxy you’re using |


### typeId List
### 1. Static Proxy List

* `1` : socks5
* `2` : http
* `3` : https

### 2. Dynamic Proxy List

- `21` IPHTML
- `22` kookeey
- `23` Lumatuo(BrightData)
- `24` Proxyma
- `25` SmartProxy
- `26` RolaIP
- `27` NodeMaven
- `29` KookeeyMobile

## Request Example

```json
{
 "id": "528086284158239744",
 "name": "api update",
 "remark": "api remark",
 "tagIDs": ["528989565877355520", "528989565877289984"],
 "groupID": "528995439832269824",
 "proxyConfig": {
 "typeId": 1,
 "server": "123.123.123.123",
 "port": 32080,
 "username": "username",
 "password": "password"
 },
 "proxyId": "528989565877355520"
}
```

## Response Example

Success Response

```json
{
 "traceId": "B04B0843BD86D9589AB3BAB6A9EA3D92",
 "code": 0,
 "msg": "success"
}
```

If some tags in the tag list do not exist, there will be `failDetails` data; if none of the tags exist, the request will directly return an error, with the `code` details as shown in the **Error Codes** section below.

```json
{
 "traceId": "8B38AA778DBCD9519FB9B00D8A593DB3",
 "code": 0,
 "msg": "success",
 "data": {
 "failDetails": [
 {
 "code": 43022,
 "id": "52898956587728998",
 "msg": "tag not found"
 }
 ]
 }
}
```

## Response Data Description

| Parameter Name | Type | Description |
| -------------- | ----------------- | -------------------------- |
| failDetails | array[FailDetails] | Tag addition failure info |

### failDetails Tag Addition Failure Info <FailDetails>

| Parameter Name | Type | Description |
| -------------- | ------- | ----------- |
| code | integer | Error code |
| id | integer | Tag ID |
| msg | string | Error msg |

## Error Codes

Below are the specific error codes for this interface. For other error codes, please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description |
| ---------- | ---------------------------------- |
| 42001 | Cloud phone does not exist |
| 43022 | Tag does not exist |
| 43032 | Group does not exist |
| 45003 | Proxy region not allowed |
| 45004 | Proxy check failed, check config |
| 45008 | Proxy type not allow |
