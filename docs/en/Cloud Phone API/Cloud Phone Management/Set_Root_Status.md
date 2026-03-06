[TOC]

## API Description
Set root status, please start the cloud phone before setting root status.

## Request URL

- `https://openapi.geelark.com/open/v1/root/setStatus`

## Request Method

- POST

## Request Parameters

| Parameter Name | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| ids | Yes |array[string] | List of cloud phone IDs ( currently supports Android 12,13,14,15 ) | Refer to request example |
| open | Yes | bool | open/close | false |


## Request Example
```json
{
    &quot;ids&quot; : [
        &quot;526209711930868736&quot;
    ],
    &quot;open&quot; : true
}
```



## Response Example

```json
{
    &quot;traceId&quot;: &quot;A24A3089958A4BC28E8B89B3AE1A61AC&quot;,
    &quot;code&quot;: 0,
    &quot;msg&quot;: &quot;success&quot;,
	&quot;data&quot;: {
        &quot;items&quot;: [
            {
                &quot;code&quot;: 42002,
                &quot;msg&quot;: &quot;phone is not running&quot;,
                &quot;id&quot;: &quot;543483007558772199&quot;
            },
            {
                &quot;code&quot;: 0,
                &quot;msg&quot;: &quot;success&quot;,
                &quot;id&quot;: &quot;543483063829554663&quot;
            }
        ]
    }
}
```


## Error Codes

For error codes, please refer to [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes).

| Error Code | Description                        |
| ---------- | ---------------------------------- |
| 42001 | cloud phone not found |
| 42002 | cloud phone is not running |
| 43016 | this cloud phone does not support root |
