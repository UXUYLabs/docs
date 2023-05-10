# Resolve DID Name

## <mark style="color:blue;">GET</mark> /api/v1/getAddress

* Note:  name-resolving services.
* Header

| Field         | Type   | Remarks                                                                                           |
| ------------- | ------ | ------------------------------------------------------------------------------------------------- |
| ApiKey        | String | ApiKey acquired from the admin                                                                    |
| Authorization | String | Bearer ${unifiedAuthToken} , in which the unifiedAuthToken is the result returned by /api/v1/auth |

* Request Parameters

| Field | Type   | Remarks                 |
| ----- | ------ | ----------------------- |
| did   | string | did name, eg: jack.uxuy |

* Request Example

```shell
curl GET 'https://api.uxuy.io/api/v1/getAddress?did=jack.uxuy \
--header 'Authorization: Bearer ey1JhbGciOiJFUzI1NiJ9.eyJqdGkiOiIyYzAzYTMwZGY4NjY0Mjk5OWZlMDcwODhh1MzVhNGU0YiIsImlzcyI6InJlbGF0aW9ubGFicy5haSIsImlhdCI6MTY2MTQwNTQxOSwic3ViIjoiYmFmMzQta2lhYWEtYWFhYWstYWNnamEtY2FpIiwiZXhwIjoxNjYyMDEwMjE5fQ.1EVbUxmtVCm6aEVZtEAji1KuCM1dsZEOMExcYvT-GdKrHRQ1qzyghXsNZSdSDUAwoSe9jGV48_1zdi2Rlrylw3Q' \
--header 'ApiKey: <ApiKey>'
```

* Response Parameters

| Field | Type   | Remarks            |
| ----- | ------ | ------------------ |
| code  | String | the Return Code    |
| msg   | String | the Return Message |
| data  | T      | the Data           |

The data field consists of the following subfields:

| Field   | Type   | Remarks                   |
| ------- | ------ | ------------------------- |
| address | String | the address of did owner  |

* Response Body

```json
{
    "code": "200",
    "msg": "ok",
    "data": {
        "address": "0x0e35437927f8080b48124cdf89eb64CD15b934644"
    }
}
```

* Return Code

| code | desc    | Remarks                           |
| ---- | ------- | --------------------------------- |
| 200  | success | the flag for a successful request |
