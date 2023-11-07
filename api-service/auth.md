# 🎊 Auth

## <mark style="color:green;">POST</mark> /api/v1/auth

* Note: To use an "addressAuthToken" in exchange for a "unifiedAuthToken" valid for 7 days.
* Header

| Field  | Type   | Remarks                        |
| ------ | ------ | ------------------------------ |
| ApiKey | String | ApiKey acquired from the admin |

* Request Example

```shell
POST /api/v1/auth
curl  POST 'https://api.uxlink.io/api/v1/auth' \
--header 'ApiKey: <ApiKey>' 
```

* Response Parameters

| Field | Type   | Remarks            |
| ----- | ------ | ------------------ |
| code  | String | the Return Code    |
| msg   | String | the Return Message |
| data  | T      | the Data           |

The Data field consists of the following subfields:

| Field | Type   | Remarks                                                                          |
| ----- | ------ | -------------------------------------------------------------------------------- |
| token | String | unifiedAuthToken. Other APIs' "Authorization" field = Bearer ${unifiedAuthToken} |

* Response Example

```json
{
    "code": "200",
    "msg": "ok",
    "data": {
        "token": "eyJhbGciOiJFUzI1NiJ9.eyJqdGkiOiJiOTE5N1Y1OGJmYTY0NDRlYmU2ODA1OTc2MmViNzdlZSIsImlzcyI6InJlbGF0aW9ubGFicy5haSIsImlhdCI6MTY2MDgyNDM0MSwic3ViIjoiYmFmMzQta2lhYWEtYWFhYWstYWNnamEtY2FpIiwiZXhwIjoxNjYxNDI5MTQxfQ.Y_1NR0N3NgQCzaR1owS6Ga4AbOIfvH7ucZJJ9-HUK_FrXBtG_WjTa3XNDfmHZIwCFDOzAjSHNcRdDaR0NZGUIw"
    }
}
```

* Return Code

| code | desc    | Remarks                           |
| ---- | ------- | --------------------------------- |
| 200  | success | the flag for a successful request |
