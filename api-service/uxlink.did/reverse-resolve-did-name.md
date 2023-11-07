# Reverse Resolve DID Name

## <mark style="color:blue;">GET</mark> /api/v1/getName

* Note:  reverse-name-resolving services.&#x20;
* Header

| Field         | Type   | Remarks                                                                                           |
| ------------- | ------ | ------------------------------------------------------------------------------------------------- |
| ApiKey        | String | ApiKey acquired from the admin                                                                    |
| Authorization | String | Bearer ${unifiedAuthToken} , in which the unifiedAuthToken is the result returned by /api/v1/auth |

* Request Parameters

| Field   | Type   | Remarks      |
| ------- | ------ | ------------ |
| address | string | user address |

* Request Example

```shell
curl  GET 'https://api.uxlink.io/api/v1/userInfo?address=0x9bd286ef4e3d9ec1af6c6ae9da2f0b3617deab13' \
--header 'ApiKey: <ApiKey>'
```

* Response Parameters

| Field | Type   | Remarks            |
| ----- | ------ | ------------------ |
| code  | String | the Return Code    |
| msg   | String | the Return Message |
| data  | T      | the Data           |

The data field consists of the following subfields:

| Field | Type   | Remarks  |
| ----- | ------ | -------- |
| did   | String | did name |

* Response Body

```json
{
    "code": "200",
    "msg": "ok",
    "data": {
        "did": "jack.uxuy"
    }
}
```

* Return Code

| code | desc    | Remarks                           |
| ---- | ------- | --------------------------------- |
| 200  | success | the flag for a successful request |
