
- GeeLark will push some operation results to developers via Webhook. After setting the Webhook URL, developers can handle these events, For common callback types, please refer to:[Callback Type](https://open.geelark.com/api/callback-type "Callback Type")

### Interface Authentication
User-defined callback interface authentication is consistent with the authentication for requesting the Geelark API.

- The request method should be set to `POST`.
- Properly receive `request header information`.
- Only one of the token verification and key verification needs to be handled.
- Set `Content-Type` to `application/json`.

#### Required Request Headers for Key Verification

- `appId` Team AppId
- `traceId` Unique request ID
- `ts` Millisecond timestamp
- `nonce` Random number
- `sign` Signature result

#### Key Verification Parameter Generation Method

- `traceId` Use `Version 4 UUID`
- `nonce` Use the first 6 characters of `traceId`
- `sign` Concatenate the string `Team AppId` + `traceId` + `ts` + `nonce` + `Team AppKey`, and use the `SHA256` hexadecimal uppercase digest of the string

#### Token Verification

When making a request, the following request headers will be carried

- `traceId` Unique request ID
- `Authorization` Set to `Bearer: <The token value obtained from the GeeLark client>`

### Cloud Phone Start Callback Received Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| type | Yes | integer | Callback event type | 1: Boot event |
| id | Yes | string | Cloud Phone ID | See example |
| result | Yes | boolean | Execution result | true: Success, false: Failure |
| username | Yes | string | Username | admin@geelark.com |
| ip | Yes | string | user ip | 62.141.247.218 |
| eventTime | Yes | interger | Time stamp in seconds | 1766567054 |

#### Example of Cloud Phone Start Callback Received Parameters

```json
{
	"type": 1,
	"id": "528086321789535232",
	"result": true,
	"username" : "admin@geelark.com",
	"ip" : "62.141.247.218",
	"eventTime" : 1766567054
}
```

### Upload files to the cloud phone Callback Received Parameters

| Parameter Name | Description |
| --- | --- |
| type | 4: Plugin installation |
| id | Cloud Phone ID |
| taskId | Task ID |
| result | Execution result: true: Success, false: Failure |

#### Example of Upload files to the cloud phone Callback Received Parameters

```
{
    "type": 4,
    "id": "528715748189668352",
	"taskId": "128715748189668352",
    "result": true,
}
```

### Cloud phone screenshot callback Received Parameters

| Parameter Name | Description |
| --- | --- |
| type | 5 |
| id | Cloud Phone ID |
| taskId | Task ID |
| result | Execution result: true: Success, false: Failure |
| downloadLink | Download Link |

#### Example of Cloud phone screenshot callback Received Parameters

```
{
    "type": 5,
    "id": "528715748189668352",
	"taskId": "128715748189668352",
    "result": true,
	"downloadLink": "https://www.abc.com/a.jpg"
}
```


### Task completion Callback Received Parameters

| Parameter Name | Description |
| --- | --- |
| type | 6: Task completion |
| taskId | Task ID |
| result | Execution result: true: Success, false: Failure |

#### Example of Task completion Callback Received Parameters

```
{
    "type": 6,
	"taskId": "528715748189668352",
    "result": true
}
```

### Cloud Phone Stop  Callback Received Parameters

| Parameter | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| type | Yes | integer | Callback event type | 8: Stop event |
| id | Yes | string | Cloud phone ID | See example |
| username | Yes | string | Username | admin@geelark.com |
| ip | Yes | string | user ip | 62.141.247.218 |
| eventTime | Yes | interger | Time stamp in seconds | 1766567054 |
| useMin | Yes | interger |Usage duration (in minutes)| 12 |

#### Example of Cloud Phone Stop  Callback Received Parameters

```json
{     
	"type": 8,
	"id": "528086321789535232" ,
	"username" : "GeeLark",
	"ip" : "62.141.247.218",
	"eventTime" : 1766567054,
	"useMin": 1
}
```

### Cloud Phone Serial Name Change Callback Parameter

| Parameter Name | Description |
| --- | --- |
| type | 9: Cloud phone serial name change |
| id | Cloud Phone ID |
| name | New serial name |

#### Example of Cloud Phone Serial Name Change Callback Parameter

```
{
	"type": 9,
	"items": [
		{
			"id" : "583502967211075086",
			"name" : "newName"
		}
	]
}
```

### Cloud Phone Delete Callback Parameter

| Parameter Name | Description |
| --- | --- |
| type | 10: Cloud phone delete |
| id | Cloud Phone ID |
| recycle | Wether deleted to the trash |

#### Example of Cloud Phone Delete Callback Parameter

```
{
	"type": 10,
	"items": [
		{
			"id" : "583502967211075086",
			"recycle" : false
		}
	]
}
```

### Cloud Phone Tag Change Callback Parameters

| Parameter | Description |
| --- | --- |
| type | 11:Cloud Phone Tag Change|
| envIds | Array of cloud phone IDs |

#### Example of Cloud Phone Tag Change Callback Parameters

```
{
	"type": 11,
	"envIds" : ["583502967211075086"]
}
```

### Task Creation Callback Parameter Receiver

| Parameter | Description |
| --- | --- |
| type | The task creation callback type is 12 |
| taskIds | Task ID |
| channel | Triggering channel, api, client |

#### Example of Task Creation Callback Parameter Receiver

```
{
    "type": 12,
	"taskIds": ["528715748189668352"],
    "channel": "api"
}
```

### Task Cancellation Callback Parameter Receiver

| Parameter | Description |
| --- | --- |
| type | The task cancellation callback type is 13 |
| taskIds | Task ID |
| channel | Triggering channel, api, client |

#### Example of Task Cancellation Callback Parameter Receiver

```
{
    "type": 13,
	"taskIds": ["528715748189668352"],
    "channel": "api"
}
```

### Callback Parameters for Cloud Phone Batch Import Contacts

| Parameter | Description |
| --- | --- |
| type | Type value is 14 |
| taskId | Task ID |
| status | Status: 0 = Failed, 1 = Successful |

#### Example of Callback Parameters for Cloud Phone Batch Import Contacts
```
{
    "type": 14,
	"taskId": "528715748189168352",
    "status": 1
}
```

### Cloud phone app installation callback parameter reception

| Parameter | Description |
| --- | --- |
| type | type is 15 |
| packageName | Application package name |
| appVersionId | Application version ID |
| id | Cloud phone ID |
| result | Installation result, 0 failures, 1 success |

#### Example of receiving parameters during cloud phone app installation callback

```
{
	"type": 15,
	"packageName": "com.example.app",
	"appVersionId": "1793552962140770305",
	"id": "528715748189168352",
	"result": 1
}
```

