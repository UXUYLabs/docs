# 🍐 Signature

* Description: The server for Signature Authentication would authenticate the incoming signature. If it is valid, then an **addressAuthToken** valid for 7 days will be returned.
* This method is packed in the JS-SDK. It is remmended to acquire the addressAuthToken through the [JS-SDK](../jssdk/social-auth/quick-start.md).
* Request Parameters

| Field              | Type    | Remarks                                                                                                                                      |
| ------------------ | ------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| pk                 | text    | Public Key (without the "0x" prefix)                                                                                                         |
| algorithm          | variant | Signature Algorithm: secp256k1;                                                                                                              |
| message            | text    | Plaintext message to be signed.**Note**：It should end with **Timestamp:${value}**, in which "value" is the current timestamp in milliseconds |
| wallet\_name       | text    | use the wallet with this name to sign the message                                                                                            |
| decoded\_signature | text    | The hexString of the signature (without the "0x" prefix)                                                                                     |
| chain\_name        | text    | the name of the blockchain                                                                                                                   |

* Request Example

```bash
curl -X POST 'https://hq6y7-wyaaa-aaaak-qas6q-cai.raw.ic0.app/auth' \
--header 'Content-Type: application/json' \
--data-raw '{"pk":"04143eed07769827d515ecf988579d228e287e692abfb7709af8c08bf300273b99de46ec375e3e68b5474d7612c72632751908a4fd75c86de90c486d54c352e8bdd","algorithm":{"secp256k1":null},"message":"Welcome to relation. Pleaes Click to sign in.Timestamp:1660839628000","wallet_name":"metamask","decoded_signature":"22aabbfab4c44e296fe3f64bcec0f6496298083266c2167d2afc9442cea785b919c9a6ffc0ae494671c50e9a3b6fa9b6ec42cb6d0b0e3f759928aefcd6d4433d1c","chain_name":"eth"}'
```

* Response Example

```json
{
    "code": "success",
    "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJFUzI1NiJ9.eyJleHAiOjE2NzExNDE4MDcsImlhdCI6MTY2MTA2MTgwNywic3ViIjoie1wiYWNjb3VudFNvdXJjZVwiOlwiZXRoXCIsXCJhZGRyZXNzXCI6XCIweDJlOGU5MWQzZTMxNTA1ZWZhNTRiMzg4YzVlOWU0OGJhNzIxNzNhY2VcIixcInVzZXJQcmluY2lwYWxcIjpcIlwifSJ9.-6Rwv_xolDvnqZgmdih7RfkTcZ4myILvyBlMyTJQddDOJGplvqZm1N95q4K_MtwLdOKoZMYoZzfKlInt4Zqb0g"
}
```
