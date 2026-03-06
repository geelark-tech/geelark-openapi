[TOC]

## API Description

- Transfer Cloud Phone

## Request URL

- `https://openapi.geelark.com/open/v1/phone/transfer`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| account | yes | string | target account | Anna@geelark.com |
| ids | yes | array[string] | The maximum length limit for the array of the cloud phone ID to be transferred is 200, and any part exceeding 200 will be ignored | |
| transferOption | no | arrry[string] |Transfer options with optional parameters：name：cloud phone name，proxy：cloud phone proxy，tag：cloud phone tag，remark：cloud phone remark，files：cloud phone files | [ &quot;name&quot;,&quot;proxy&quot;, &quot;tag&quot;,&quot;remark&quot; ]| 

## Request Example

```json
{
    &quot;ids&quot;: [
        &quot;539893235657500146&quot;
    ],
    &quot;account&quot;: &quot;Anna@geelark.com&quot;,
    &quot;transferOption&quot;: [
        &quot;name&quot;,
        &quot;proxy&quot;,
        &quot;tag&quot;,
        &quot;remark&quot;
    ]
}
```


## Response Example

```json
{
	&quot;traceId&quot;: &quot;B0BA8FF29AB60B8ABF4E9A26BF08F7B9&quot;,
	&quot;code&quot;: 0,
	&quot;msg&quot;: &quot;success&quot;,
	&quot;data&quot;: [
		{
			&quot;successCount&quot;: 10,
			&quot;failCount&quot;: 2,
			&quot;failEnvIds&quot; : [&quot;539893235657500146&quot;]
		}
	]
}
```

## Response Data Description

| Parameter Name | Type | Description |
| ----------- | -----------|----------- |
| successCount | int | success count|
| failCount | int | fail count|
| failEnvIds | array[string] | transfer failed cloud phone id (currently in use or does not exist)|


Error Codes
-----------

For error codes, please refer to  [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes)


| Error Code | Description |
| --- | --- |
| 40013 | target account not found |
| 43022 | can not transfer to myself |


