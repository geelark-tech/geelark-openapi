[TOC]

## Overview

- Support local API functions
- All interface requests are initiated using `POST`.
- All request bodies are in `json` format. Please set the `Content-Type` request header to `application/json`.
- API rate limit: 200 times/min, 24,000 times/hour
- Preparation before use:
	Check whether the client is open and logged in.

## Response Description

When the response code is `200`, the response body is `json`

### Response body object fields

- `traceId` Request unique ID.
- `code` Processing result code, 0 represents success, other codes represent failure.
- `msg` Description of the processing result.
- `data` The details are as follows:
 When the request is successful, the response data is returned.
If the request fails, the failure reason is returned.
If the request is partially successful, the response data and the failure reason are returned.

### Processing result code description

0 indicates success, and other values indicate failure.
If an error code appears, try modifying the request according to the prompts.
If the problem persists, please contact customer service for feedback.
In addition to the global error code, the error code corresponding to each interface is documented in its respective description. The global error codes are as follows:

- `40000` Unknown error. If this occurs, please contact customer service.
- `40001` Failed to read the request body. If this occurs, please contact customer service.
- `40002` The `traceId` header in the request cannot be empty.
- `40003` Signature verification failed.
- `40004` Request parameter verification failed.
- `40005` The requested resource does not exist.
- `40006` The request was partially successful. This applies to batch interfaces.
- `40007` Requests are too frequent. The rate limit will be lifted in the next minute.
- `40008` Pagination parameter error.
- `40009` All batch processing failed.
- `40011` Only for paid users.
- `41001` Insufficient balance.
- `40012` The interface has expired. Please use the latest interface.
- `47002` The number of concurrent requests is too high. Please try again later.
- `40014` Requests are too frequent. The rate limit will be lifted in two hours.
- `90000` Request parameter verification failed.
- `90001` User not logged in
- `90004` The user does not have browser API permissions.
