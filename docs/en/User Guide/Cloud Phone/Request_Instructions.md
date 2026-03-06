[TOC]

Request Instructions
--------------------

* All API requests must be initiated using `POST`.
* All request bodies should be in `JSON` format. Please set the request header `Content-Type` to `application/json`.
* There are two verification methods, including key verification and token verification.
* Per API rate limit: 200 requests per minute, 24,000 requests per hour

### Token verification

When making a request, only carry the following request headers

- `traceId`: Use `Version 4 UUID`
- `Authorization` Set to `Bearer &lt;The token value obtained from the client&gt;`

Response Instructions

### Key verification

#### Required Request Headers for Verification

* `appId`: Team AppId
* `traceId`: Unique request ID
* `ts`: Timestamp in milliseconds
* `nonce`: Random number
* `sign`: Signature result

#### Verification Parameter Generation Method

* `traceId`: Use `Version 4 UUID`
* `nonce`: Use the first 6 characters of `traceId`
* `sign`: Concatenate the string `TeamAppId` + `traceId` + `ts` + `nonce` + `TeamApiKey`, then generate the `SHA256` hexadecimal uppercase digest of the string.

#### Example of Required Request Headers for Verification

Assuming the team&#039;s ApiKey is `YjmFIUuq0oJgSDJ42fxLEb6R1qjjqf`, the request headers would be set as follows:

* `appId`: `eH6gQR4oHr3FsZpI36La01IW`
* `traceId`: `db6094ab-3797-4186-84d5-b0b58eebad56`
* `ts`: `1716972892166`
* `nonce`: `db6094`
* `sign`: `6280C080AF7C3CCE168F15C913E3444A00A618CB0E16038EED9811D6E3366BDD`

---------------------

When the response code is `200`, the response body will be in `JSON` format.

### Response Object Fields

* `traceId`: Unique request ID.
* `code`: Processing result code, `0` indicates success, any other value indicates failure.
* `msg`: Processing result description.
* `data`: Data. Details are as follows:
 * On successful request: returns response data.
 * On failed request: returns the reason for failure.
 * On partially successful request: returns response data and reason for failure.

### Processing Result Code Explanation

`0` indicates success, any other value indicates failure. If an error code appears, try modifying the request based on the prompt. If the issue persists, please contact customer service and provide the `appId`, `traceId`, and the response content. Apart from global error codes, error codes specific to each API are documented in their respective descriptions. Global error codes are as follows:

* `40000`: Unknown error, please contact customer service if this occurs.
* `40001`: Failed to read request body, please contact customer service if this occurs.
* `40002`: The `traceId` in the request header cannot be empty.
* `40003`: Signature verification failed.
* `40004`: Request parameter validation failed.
* `40005`: Requested resource does not exist.
* `40006`: Partial success in the request, applicable to batch APIs.
* `40007`: Too many requests.The rate limit will be lifted in the next minute.
* `40008`: Invalid pagination parameters.
* `40009`: Batch processing completely failed.
* `40011`: Only for paid user.
* `41001`: Balance not enough.
* `40012`: The api had expire, please use the new api.
* `47002`: Too many concurrent requests. Please try again later.The rate limit will be lifted after two hours.