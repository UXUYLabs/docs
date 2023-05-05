# 🎊 Auth

## <mark style="color:green;">POST</mark> /api/v1/auth

* Note: To use an "addressAuthToken" in exchange for a "unifiedAuthToken" valid for 7 days.
* Header

| Field           | Type   | Remarks                                                                                                                     |
| --------------- | ------ | --------------------------------------------------------------------------------------------------------------------------- |
| ApiKey          | String | [ApiKey](broken-reference) acquired from the admin                                                                          |
| I-Authorization | String | Bearer ${addressAuthToken},in which the addressAuthToken is acquired with a signature authenticationprocess through JS-SDK. |

* Request Parameters

| Field      | Type   | Remarks                                                               |
| ---------- | ------ | --------------------------------------------------------------------- |
| inviteCode | String | Invite Code or the relationId of the user sending out the invitation. |

* Request Example

```shell
POST /api/v1/auth
curl  POST 'https://api.relationlabs.ai/api/v1/auth' \
--header 'I-Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJFUzI1NiJ9.eyJleHAiOjE2NzA4ODk0NDEsImlhdCI6MTY2MDgwOTQ0MSwiaXNzIjoicmVsYXRpb25sYWJzLmFpIiwic3ViIjoiMHgxZTU2MmFhYzRiZWFjNDUwYWI5OGQzNzlhYjBkMWQxYjQ0YzMyNWIzIi1id2FsbGV0TmFtZSI6Im1ldGFtYXNrIiwiY2hhaW5OYW1lIjoiZXRoIn0.2wFJmR2D3inHMItBugoaVE3MOSLnG1ylJEyU38WU0GgLIqajhzvcYYHC5ah3r7-FFBhbWGk9WW3KxN_h5K1zZA' \
--header 'ApiKey: <ApiKey>' \
--header 'Content-Type: application/json' \
--data-raw '{
    "inviteCode":"d4swz-zaaaa-aaaaj-at5fa-cai"
}'
```

* Response Parameters

| Field | Type   | Remarks            |
| ----- | ------ | ------------------ |
| code  | String | the Return Code    |
| desc  | String | the Return Message |
| data  | T      | the Data           |

The Data field consists of the following subfields:

| Field | Type   | Remarks                                                                          |
| ----- | ------ | -------------------------------------------------------------------------------- |
| token | String | unifiedAuthToken. Other APIs' "Authorization" field = Bearer ${unifiedAuthToken} |

* Response Example

```json
{
    "code": "0",
    "desc": "success",
    "data": {
        "token": "eyJhbGciOiJFUzI1NiJ9.eyJqdGkiOiJiOTE5N1Y1OGJmYTY0NDRlYmU2ODA1OTc2MmViNzdlZSIsImlzcyI6InJlbGF0aW9ubGFicy5haSIsImlhdCI6MTY2MDgyNDM0MSwic3ViIjoiYmFmMzQta2lhYWEtYWFhYWstYWNnamEtY2FpIiwiZXhwIjoxNjYxNDI5MTQxfQ.Y_1NR0N3NgQCzaR1owS6Ga4AbOIfvH7ucZJJ9-HUK_FrXBtG_WjTa3XNDfmHZIwCFDOzAjSHNcRdDaR0NZGUIw"
    }
}
```

* Return Code

| code | desc    | Remarks                           |
| ---- | ------- | --------------------------------- |
| 0    | success | the flag for a successful request |
