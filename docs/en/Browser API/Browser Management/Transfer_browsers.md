[TOC]

## Interface Description

Transfer the browser to another team.


## Request URL

- `http://localhost:40185/api/v1/browser/transfer`


## Request method


- POST


## Request Parameters


| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| username | yes | string | Target user account | Anna@geelark.com |
| envIds | yes | array[string] | Environment IDs to transfer. The maximum length of the array is 200. Entries exceeding 200 will be ignored. |[&quot;539893235657500146&quot;]|
| transferOption | no | array[string] | Optional transfer option parameters: name: environment name, proxy: proxy, tag: tag, remark: remark, files: files | [ &quot;name&quot;,&quot;proxy&quot;, &quot;tag&quot;,&quot;remark&quot; ] |


## Request Example


```json
{
  &quot;envIds&quot;: [&quot;539893235657500146&quot;],
  &quot;username&quot;: &quot;Anna@geelark.com&quot;
}
```


## Example response


```json
{
    &quot;traceId&quot;: &quot;123456ABCDEF&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
    &quot;data&quot;: {
		&quot;successCount&quot;: 10,
		&quot;failCount&quot;: 2,
		&quot;failEnvIds&quot;: [&quot;539893235657500146&quot;]
    }
}
```


## Response body data description


| Parameter Name | Type | Description |
| --- | --- | --- |
| successCount | int | Number of successful transfers |
| failCount | int | Number of failed transfers |
| failEnvIds | array[string] | IDs of environments where transfers failed, including those in use or non-existent environments |


## Error Code


Below are specific error codes for this interface. For other error codes, please refer to [Browser Error Codes](https://open.geelark.com/api/browser-error-codes).


| Error Code | Description |
| --- | --- |
| 40013 | Target user account does not exist |
| 43022 | Cannot transfer to own account |
| 43027 | This browser cannot be transferred |
| 40011 | The current user is not a paying user |
| 43028 | The sub-user does not have permissions for this environment group |

