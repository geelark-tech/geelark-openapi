[TOC]

API Description
---------------

Proxy Detection API

Request URL
-----------

*   `https://openapi.geelark.com/open/v1/proxy/check`
    

Request Method
--------------

*   POST
    

Request Parameters
------------------

| Parameter | Required | Type | Description | Example |
| --- | --- | --- | --- | --- |
| detect\_type | Yes | string | IP lookup source, supports only `IP-API` or `IP2Location` | IP2Location |
| proxy\_type | Yes | string | Proxy type, supports only `socks5`, `http`, or `https` | socks5 |
| server | Yes | string | Host | 185.162.130.86 |
| port | Yes | int | Port number | 11000 |
| username | No | string | Proxy username | username |
| password | No | string | Proxy password | pass |

Request Example
---------------
```json
{
	&quot;detect_type&quot;: &quot;IP2Location&quot;,
	&quot;proxy_type&quot;: &quot;socks5&quot;,
	&quot;server&quot;: &quot;185.162.130.86&quot;,
	&quot;port&quot;: 10000,
	&quot;username&quot;: &quot;username&quot;,
	&quot;password&quot;: &quot;pass&quot;
}
```

Response Data Description
-------------------------

| Field | Type | Description |
| --- | --- | --- |
| detectStatus | bool | Whether the detection was successful |
| message | string | Reason for failure (if any) |
| outboundIP | string | Outbound IP |
| countryCode | string | Country code of the outbound IP |
| countryName | string | Country name of the outbound IP |
| subdivision | string | State/Province of the outbound IP |
| city | string | City of the outbound IP |
| timezone | string | Time zone of the outbound IP |
| isp | string | ISP of the outbound IP |

Response Example
----------------
```json
{
	&quot;traceId&quot;: &quot;B379AA1BBBB529758ED091C480AA4285&quot;,
	&quot;code&quot;: 0,
	&quot;msg&quot;: &quot;success&quot;,
	&quot;data&quot;: {
		&quot;detectStatus&quot;: true,
		&quot;message&quot;: &quot;&quot;,
		&quot;outboundIP&quot;: &quot;223.135.25.196&quot;,
		&quot;countryCode&quot;: &quot;JP&quot;,
		&quot;countryName&quot;: &quot;Japan&quot;,
		&quot;subdivision&quot;: &quot;Tokyo&quot;,
		&quot;city&quot;: &quot;Tokyo&quot;,
		&quot;timezone&quot;: &quot;Asia/Tokyo&quot;,
		&quot;isp&quot;: &quot;Sony Network Communications Inc.&quot;
	}
}
```

Error Codes
-----------

Please refer to the [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes)
