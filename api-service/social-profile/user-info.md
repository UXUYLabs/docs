# User Info

## <mark style="color:blue;">GET</mark> /api/v1/userInfo

* Note: To return a user's information.&#x20;
* Header

| Field         | Type   | Required | Remarks                                                                                           |
| ------------- | ------ | -------- | ------------------------------------------------------------------------------------------------- |
| ApiKey        | String | true     | [ApiKey](broken-reference) acquired from the admin                                                |
| Authorization | String | false    | Bearer ${unifiedAuthToken} , in which the unifiedAuthToken is the result returned by /api/v1/auth |

* Request Parameters

| Field   | Type          | Required | Remarks                                                                                                      |
| ------- | ------------- | -------- | ------------------------------------------------------------------------------------------------------------ |
| address | String        | false    | relationId or address                                                                                        |
| fields  | List\[String] | false    | option，Fill in the user fields that need to be returned，value: CREATE\_AT、FOLLOW\_COUNT、ADDRESS\_WITH\_CHAIN |

* Request Example

```shell
curl  GET 'https://api.relationlabs.ai/api/v1/userInfo?address=0x9bd286ef4e3d9ec1af6c6ae9da2f0b3617deab13' \
--header 'ApiKey: <ApiKey>'
```

* Response Parameters

| Field | Type     | Remarks            |
| ----- | -------- | ------------------ |
| code  | String   | the Return Code    |
| desc  | String   | the Return Message |
| data  | UserInfo | the Data           |

The UserInfo field consists of the following subfields:

| Field            | Type             | Remarks                                                                              |
| ---------------- | ---------------- | ------------------------------------------------------------------------------------ |
| name             | String           | User Name                                                                            |
| avatar           | String           | User's Avatar                                                                        |
| relationId       | String           | User's relationId                                                                    |
| createdAt        | String           | User's register time                                                                 |
| followCount      | FollowCount      | Total number of followers and following                                              |
| └─followingCount | Integer          | Total number of following                                                            |
| └─followersCount | Integer          | Total number of followers                                                            |
| addressWithChain | AddressWithChain | User's address ,and the chain which the address belongs                              |
| └─address        | String           |                                                                                      |
| └─chainName      | String           | the chain name,current support：eth、polygon、bsc、op、moonbeam、solana、flow、substrate、ic、 |

* Response Example

```json
{
    "code": "0",
    "desc": "success",
    "data": {
        "relationId": "dhkyq-sqaaa-aaaaj-sgz3q-cai",
        "name": "0x1e56",
        "avatar": "",
        "createdAt": "2022-08-18 16:54:15",
        "followCount": {
            "followingCount": 1,
            "followersCount": 0
        },
        "addressWithChain": [
            {
                "address": "0xb152e0eebd5d2b98da5d1ed7d1ce066c20a4e430",
                "chainName": "eth"
            }
        ]
    }
}
```

* Return Code

| code  | desc    | Remarks                                   |
| ----- | ------- | ----------------------------------------- |
| 0     | success | the flag for a successful request         |
| 11601 | failed  | this field not support in current version |
| 11602 | failed  | user not found                            |
