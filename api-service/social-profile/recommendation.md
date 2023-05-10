# Recommendation

## <mark style="color:blue;">GET</mark> /api/v1/recommend

* Note: The recommendation engine recommends potential friends to DApp based on tags they add.
* Header

| Field         | Type   | Remarks                                                                                           |
| ------------- | ------ | ------------------------------------------------------------------------------------------------- |
| ApiKey        | String | ApiKey acquired from the admin                                                                    |
| Authorization | String | Bearer ${unifiedAuthToken} , in which the unifiedAuthToken is the result returned by /api/v1/auth |

* Request Parameters

| Field  | Type   | Remarks                                                                                            |
| ------ | ------ | -------------------------------------------------------------------------------------------------- |
| limit  | int    | Query limit (up to 100)                                                                            |
| cursor | string | Cursor data returned by last page. If it is empty, it means the caller is querying the first page. |

* Request Example

```shell
curl GET 'https://api.uxuy.io/api/v1/recommend?cursor=a604fdd8e80142dfaf07af11096d5150&limit=10' \
--header 'Authorization: Bearer ey1JhbGciOiJFUzI1NiJ9.eyJqdGkiOiIyYzAzYTMwZGY4NjY0Mjk5OWZlMDcwODhh1MzVhNGU0YiIsImlzcyI6InJlbGF0aW9ubGFicy5haSIsImlhdCI6MTY2MTQwNTQxOSwic3ViIjoiYmFmMzQta2lhYWEtYWFhYWstYWNnamEtY2FpIiwiZXhwIjoxNjYyMDEwMjE5fQ.1EVbUxmtVCm6aEVZtEAji1KuCM1dsZEOMExcYvT-GdKrHRQ1qzyghXsNZSdSDUAwoSe9jGV48_1zdi2Rlrylw3Q' \
--header 'ApiKey: <ApiKey>'
```

* Response Parameters

| Field | Type              | Remarks            |
| ----- | ----------------- | ------------------ |
| code  | String            | the Return Code    |
| msg   | String            | the Return Message |
| data  | RecommendResponse | the Data           |

The RecommendResponse field consists of the following subfields:

| Field  | Type                 | Remarks           |
| ------ | -------------------- | ----------------- |
| cursor | String               | the cursor        |
| list   | List\[RecommendUser] | list of followers |

The RecommendUser field consists of the following subfields:

| Field           | Type   | Remarks                   |
| --------------- | ------ | ------------------------- |
| uxuyId          | String | User's uxuyId             |
| name            | String | User name                 |
| avatar          | String | User's avatar             |
| recommendReason | String | Reason for recommendation |

* Response Body

```json
{
    "code": "200",
    "msg": "ok",
    "data": {
        "cursor": "a8728c5910a04c94b70e18694d72cbb0",
        "list": [
            {
                "uxutId": "sdfaert435233ret4rgfdgdfgh",
                "name": "test_user",
                "avatar": "https://thirdwx.qlogo.cn/mmopen/vi_32/ajNVdqHZLLAkZDDuorBaRk7N5eFLY9z4QEsjjLaIfH5ITaAqibkfibkTalYrhh7cnoAcvl29VeAnJMALZEUhx64Q/132",
                "recommendReason": "tags: Seaman NFT"
            },
            ...
        ]
    }
}
```

* Return Code

| code | desc    | Remarks                           |
| ---- | ------- | --------------------------------- |
| 200  | success | the flag for a successful request |
