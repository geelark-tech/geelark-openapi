## Interface Description

Used to start the browser environment with the specified ID. Supports synchronous response and asynchronous WebHook callback notification.

## Request URL

- `http://localhost:40185/api/v1/browser/start`

## Request method


- POST


## Request Parameters


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| id | Yes | string | browser id| 539893235657500146 |
|webhook|No|string|Callback URL. Notification will be sent after the browser finishes starting|http://localhost:3001

##WebHook Callback
###Trigger Timing
Triggered after the browser startup task is completed.
###Callback URL
Specified by the webhook request parameter.
###Callback Method
POST
###Callback Request Headers
```json
{
  "Content-Type": "application/json",
  "Authorization": "Bearer AZ4LY7J33IY5NQ7IYVQ5D5BR7B6GNWSG" // Same as the Authorization header in the API request
}
```
###Callback Data
```json
{
  "event": "browser_start",
  "timestamp": 1776147008407,
  "data": {
    "id": "612342716134614477",
    "status": "success",
    "debugPort": 11019,
    "ipCheckPass": true
  }
}
```


## Request Example

```json
{
  "id": "612342716134614477",
  "webhook": "http://localhost:3001"
}
```


## Example response


```json
{
  "code": 0,
  "msg": "success",
  "data": {
    "debugPort": 11001
  }
}
```


## Error Code

Below are specific error codes for this interface. For other error codes, please refer to [Browser Error Codes](https://open.geelark.com/api/browser-error-codes).


| Error Code | Description |
| --- | --- |
| -1 | Startup failed |
| 43007 | The environment is already in use |
| 43008 | The maximum number of open environments has been reached |
| 46003 | The environment is not included in the plan |
| 43028 | The sub-user does not have permissions for the environment group |
| 90002 | This environment does not exist. |
| 90003 | Insufficient disk space |