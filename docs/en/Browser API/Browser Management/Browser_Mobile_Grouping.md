## Interface description

Used to regroup environments and assign them to corresponding groups by ID.

## Request URL

- `http://localhost:40185/api/v1/browser/moveGroup`

## Request Method

- POST

## Request parameters

| Parameter name | Must be selected | Type | Example | Description
| --- | --- | --- | --- | --- |
| envIds | Yes | array[string] | ["123456789","987654321"] | browser IDs, up to 100 |
| groupId | Yes | string | "123456789" | group ID, and "0" is moved to ungrouped |

## Request example

```json
{
    "envIds":["123456789","987654321"],
    "groupId":"0"
}
```

## Response examples

```json
{
"traceId": "123456ABCDEF",
    "code": 0,
    "msg": "success",
}
```