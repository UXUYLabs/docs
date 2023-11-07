# 🗝 MPC Account

Multi-party computation (MPC) is a cryptographic tool that allows multiple parties to make calculations using their combined data, without revealing their individual input.

In contrast to a standard SOA wallet account, you do not need to keep complex private keys with an MPC Wallet account, so an MPC Wallet account is also known as a Keyless wallet account.&#x20;

\
User who joins UXLINK will receive an MPC wallet account, which will serve as their primary account for using UXLINK.

## <mark style="color:blue;">GET</mark> /api/v1/getUserMpcKey

* Note:  acquire user mpc key. When transfer or withdrawal, user need to send this part of key to uxuy system to sign. For security, each DAPP has different mpc key.
* Header

| Field         | Type   | Remarks                                                                                           |
| ------------- | ------ | ------------------------------------------------------------------------------------------------- |
| ApiKey        | String | ApiKey acquired from the admin                                                                    |
| Authorization | String | Bearer ${unifiedAuthToken} , in which the unifiedAuthToken is the result returned by /api/v1/auth |

* Request Parameters

| Field   | Type   | Required | Remarks           |
| ------- | ------ | -------- | ----------------- |
| address | String | false    | uxuyId or address |

* Request Example

```shell
curl GET 'https://api.uxlink.io/api/v1/getUserMpcKey?address=0x9bd286ef4e3d9ec1af6c6ae9da2f0b3617deab13' \
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

| Field  | Type   | Remarks |
| ------ | ------ | ------- |
| mpcKey | String | mpc key |

* Response Body

```json
{
    "code": "200",
    "msg": "ok",
    "data": {
        "mpcKey": "+d1dhW8iw+QdtzJO3248XDUXRIcL9R7YTU1V43IzDEghjCgf5Ht24d9m/uTGRFvX8aqpYtnt6jqXM4ezdzlmgKDNCp505p9R6Ciyz9WQut173qeY31gvPyOxtasveEz/N42"
    }
}
```

* Return Code

| code | desc    | Remarks                           |
| ---- | ------- | --------------------------------- |
| 200  | success | the flag for a successful request |
