# 🎊 Explorer API

> **We are not currently open to the public for our API application, please submit your information from here and we will configure a dedicated \[** [<mark style="color:green;">**DappKey**</mark>](https://forms.gle/t9kSooJJyouBa5Dt5)[​](https://docs.walletconnect.com/cloud/explorer#listings) ]

### **`POST /interfa/v1/auth`**

<table><thead><tr><th width="155">Param</th><th width="84">Type</th><th>Required?</th><th>Description</th></tr></thead><tbody><tr><td>Token</td><td>String</td><td>Required</td><td>Dappkey acquired from the <a href="https://forms.gle/t9kSooJJyouBa5Dt5">admin</a></td></tr></tbody></table>

**Returns a JSON object containing the AccessToken and RefreshToken.**

Example：

{% code overflow="wrap" %}
```bash
curl -X POST 'https://exdapps.uxlink.io/interfa/v1/auth' \
-H 'Token: <DappKey>' \
-H 'Content-Type: application/json'
```
{% endcode %}

```json
// Response Example
{
    "success": true,
    "msg": "ok",
    "code": 200,
    "data": {
        "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3NzM0ODE5OTMsImlhdCI6MTcxMDQwOTk5Mywiand0RGFwcElasdc3123oiQzI1NUtRMFBTVlk0UjZX1231DYxUjRHUTUwQ09PSVZSSVUifQ.nlg5vzO-0XjRzqg3z-90F-O1YbnRyFj8btpWyFAI_SI",
        "refreshToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3NzM0ODE5OTMsImlhdCI6MTcxMDQwOTk5Mywiand0RGFwcElkIjoiQzI1NUtRMFBTVlk0UjROVDYxUjRasas2ewQ09PSVZSSVUifQ.nlg5vzO-0XjRzqg3z-90F-O1YbnRyFj8btpWyFAI_SI",
        "accessExpire": 162341315435,
        "refreshAfter": 162341315435
    }
}
```



### **`POST /interfa/v1/login/account`**

<table><thead><tr><th width="155">Param</th><th width="84">Type</th><th>Required?</th><th>Description</th></tr></thead><tbody><tr><td>Authorization</td><td>String</td><td>Required</td><td>Get AccessToken from /interfa/v1/auth</td></tr><tr><td>address</td><td>String</td><td>Required</td><td>Wallet Address</td></tr></tbody></table>

**Returns a JSON object providing the user's information, AccountInfo.**

Example：

{% code overflow="wrap" %}
```bash
curl -X POST 'https://exdapps.uxlink.io/interfa/v1/login/account' \
-H 'Authorization: <AccessToken>' \
-H 'Content-Type: application/json' \
-d '{
  "address": "0xc593e54A2016ea8FD71a4F62974BeC65f74C909C",
}'
```
{% endcode %}

```json
// Response Example:
{
    "success": true,
    "msg": "ok",
    "code": 200,
    "data": {
	"accountInfo": {
            "uxuyId": "4A2016ea8X2dsa2", //userId
            "name": "uxlink",
            "avatar": "https://avatar.jpg", 
            "address": "0xc593e54A2016ea8FD71a4F62974BeC65f74C909C", //UXWallet Address
        }
    }
}
```



### `POST /interfa/v1/user/relation/list`

<table><thead><tr><th width="155">Param</th><th width="84">Type</th><th>Required?</th><th>Description</th></tr></thead><tbody><tr><td>Authorization</td><td>String</td><td>Required</td><td>Get AccessToken from /interfa/v1/auth</td></tr><tr><td>pageSize</td><td>Int</td><td>Required</td><td>20</td></tr><tr><td>nextToken</td><td>String</td><td>Required</td><td>pageSize can be null if it is 1, otherwise get it in the returned JSON.</td></tr><tr><td>address</td><td>String</td><td>Required</td><td>Wallet Address</td></tr></tbody></table>

**Returns a JSON object, i.e. the user's social data.**

Example：

```bash
curl -X POST 'https://exdapps.uxlink.io/interfa/v1/user/relation/list' \
-H 'Authorization: <AccessToken>' \
-H 'Content-Type: application/json' \
-d '{
  "pageSize": 20,
  "nextToken": "eyJleHAiOjE3NzM0ODE5OTMsImlhdCI6MTcxMDQwOTk5Mywiand0RGFwcElkIjoiQzI1NUtRMFBTVlk0UjROVDYxUjRasas2ewQ09PSVZSSVUifQ",
  "address": "0xc593e54A2016ea8FD71a4F62974BeC65f74C909C"
}' 
```

```json
// Response Example:
{
    "success": true,
    "msg": "ok",
    "code": 200,
    "data": {
      "pageSize": 20, 
      "nextPage": true,
      "nextToken": "eyJleHAiOjE3NzM0ODE5OTMsImlhdCI",
	   "list": [
	       {
		  "uxuyId": "12313100000000", 
		  "name": "ali", 
		  "avatar": "https://dsdfsdfs.jpg", 
	          "address": "0x24234234234234", 
	       },
            ]
    }
}
```



### `POST /interfa/v1/user/token/total`

<table><thead><tr><th width="155">Param</th><th width="84">Type</th><th>Required?</th><th>Description</th></tr></thead><tbody><tr><td>Authorization</td><td>String</td><td>Required</td><td>Get AccessToken from /interfa/v1/auth</td></tr><tr><td>address</td><td>String</td><td>Required</td><td>Wallet Address</td></tr></tbody></table>

**Returns a JSON object that looks up the balance of the user's wallet account.**

Example：

{% code overflow="wrap" %}
```bash
curl -X POST 'https://exdapps.uxlink.io/interfa/v1/user/token/total' \
-H 'Authorization: <AccessToken>' \
-H 'Content-Type: application/json' \
-d '{
  "address": "0xc593e54A2016ea8FD71a4F62974BeC65f74C909C",
}' 
```
{% endcode %}

```json
// Response Example:
{
    "success": true,
    "msg": "ok",
    "code": 200,
    "data": {
        "totalUsdValue": 27654.142997146177,
	"chainList": [
		{
		      "id": "eth",
		      "communityId": 1,
		      "name": "Ethereum",
		      "nativeTokenId": "eth",
		      "logoUrl": "https://static.debank.com/image/chain/logo_url/eth/42ba589cd077e7bdd97db6480b0ff61d.png",
		      "wrappedTokenId": "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2",
		      "usdValue": 11937.702345945296,
		      "percent": 34.2 // Current chain assets as a percentage of total chain
		}
	]
   }
}
```



### `POST /interfa/v1/user/token/list`

<table><thead><tr><th width="155">Param</th><th width="84">Type</th><th>Required?</th><th>Description</th></tr></thead><tbody><tr><td>Authorization</td><td>String</td><td>Required</td><td>Get AccessToken from /interfa/v1/auth</td></tr><tr><td>address</td><td>String</td><td>Required</td><td>Wallet Address</td></tr><tr><td>chainId</td><td>String</td><td>Optional</td><td>Only single choice or do not fill in, do not fill in is the full chain</td></tr></tbody></table>

**Return a JSON object, i.e. query the user's wallet asset details.**

Example：

```bash
curl -X POST 'https://exdapps.uxlink.io/interfa/v1/user/token/list' \
-H 'Authorization: <AccessToken>' \
-H 'Content-Type: application/json' \
-d '{
  "address": "0xc593e54A2016ea8FD71a4F62974BeC65f74C909C",
  "chainId": "eth"
}' 
```

```json
// Response Example:
{
    "success": true,
    "msg": "ok",
    "code": 200,
    "data": {
        "list": [
		  {
                     "id": "0x0000000000004946c0e9f43f4dee607b0ef1fa1c",
                     "chain": "eth",
                     "name": "Chi Gastoken by 1inch",
                     "symbol": "CHI",
                     "optimizedSymbol": "CHI",
                     "decimals": 18,
                     "logoUrl": "https://static.debank.com/image/eth_token/logo_url/0x0000000000004946c0e9f43f4dee607b0ef1fa1c/5d763d01aae3f0ac9a373564026cb620.png",
                     "protocolId": "1inch",
                     "price": 0,
                     "isCore": true,
                     "isWallet": true,
                     "timeAt": 1546294558,
                     "amount": 21.709487132565773,
                     "rawAmount": "21709487132565774000" // Raw amount, based on decimal to determine decimal places
                     "usdValue": 21.3333, // Corresponding usd value
                  },
                  {...}
         ]
   }
}
```



### &#x20;Code

| Code    | Desc    | Remarks                           |
| ------- | ------- | --------------------------------- |
| 200     | success | the flag for a successful request |
| 5001002 | false   |                                   |
