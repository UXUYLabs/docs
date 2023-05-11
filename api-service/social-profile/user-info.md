# User Info

## <mark style="color:blue;">GET</mark> /api/v1/userInfo

* Note: To return a user's information.&#x20;
* Header

| Field         | Type   | Required | Remarks                                                                                           |
| ------------- | ------ | -------- | ------------------------------------------------------------------------------------------------- |
| ApiKey        | String | true     | [ApiKey](broken-reference) acquired from the admin                                                |
| Authorization | String | false    | Bearer ${unifiedAuthToken} , in which the unifiedAuthToken is the result returned by /api/v1/auth |

* Request Parameters

| Field   | Type   | Required | Remarks           |
| ------- | ------ | -------- | ----------------- |
| address | String | false    | uxuyId or address |

* Request Example

```shell
curl  GET 'https://api.uxuy.io/api/v1/userInfo?address=0x9bd286ef4e3d9ec1af6c6ae9da2f0b3617deab13' \
--header 'Authorization: Bearer ey1JhbGciOiJFUzI1NiJ9.eyJqdGkiOiIyYzAzYTMwZGY4NjY0Mjk5OWZlMDcwODhh1MzVhNGU0YiIsImlzcyI6InJlbGF0aW9ubGFicy5haSIsImlhdCI6MTY2MTQwNTQxOSwic3ViIjoiYmFmMzQta2lhYWEtYWFhYWstYWNnamEtY2FpIiwiZXhwIjoxNjYyMDEwMjE5fQ.1EVbUxmtVCm6aEVZtEAji1KuCM1dsZEOMExcYvT-GdKrHRQ1qzyghXsNZSdSDUAwoSe9jGV48_1zdi2Rlrylw3Q' \
--header 'ApiKey: <ApiKey>'
```

* Response Parameters

| Field | Type     | Remarks            |
| ----- | -------- | ------------------ |
| code  | String   | the Return Code    |
| desc  | String   | the Return Message |
| data  | UserInfo | the Data           |

The UserInfo field consists of the following subfields:

| Field     | Type   | Remarks              |
| --------- | ------ | -------------------- |
| name      | String | User Name            |
| avatar    | String | User's Avatar        |
| did       | String | User's DID           |
| uxuyId    | String | User's uxuyId        |
| createdAt | String | User's register time |

* Response Example

```json
{
    "code": "0",
    "desc": "success",
    "data": {
        "uxuyId": "g23rerg34tgf235yr3463245",
        "name": "0x1e56",
        "avatar": "",
        "did": "jack.uxuy",
        "createdAt": "2023-05-10 10:54:14"
    }
}
```

* Return Code

| code | desc    | Remarks                           |
| ---- | ------- | --------------------------------- |
| 0    | success | the flag for a successful request |
