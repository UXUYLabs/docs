---
description: 在引用一下api需要获取到token，否则会出现错误提示
---

# Account api

## &#x20;Method

#### getUserInfo(userid:string)

> #### 获取个人用户信息

```typescript
account.getUserInfo('userid')
```

####

#### updateUserInfo(userName: string, userAvatar: string, userGender: number)

> #### 更新用户个人信息

```typescript
account.updateUserInfo('username', 'userAvatarUrl', 0)
```

| **Parameter** | **Type** | **Description**          | **Default** |
| ------------- | -------- | ------------------------ | ----------- |
| userName      | string   | 字段长度不得超过 130 个字符，支持特殊字符  |             |
| userAvatar    | string   | 目前只支持IPFS，CDN资源，未来支持 NFT |             |
| userGender    | Number   | <p>0: <br>1：<br>2</p>    | 0           |

####

#### usetSocialRelationList( pageNum: string, pageSize: string )

> 获取个人的好友列表

```typescript
account.updateUserInfo(1, 20)
```

| **Parameter** | **Type** | **Description** | **Default** |
| ------------- | -------- | --------------- | ----------- |
| pageNum       | string   | 当前页数            | 1           |
| pageSize      | string   | 列表数量            | 10          |

####

#### assetsShow()

> 获取个人资产（UXUY）

```typescript
account.assetsShow()
```

####

#### claimToken()

> Claim UXUY Token

```typescript
account.claimToken()
```



#### getAccountRecord( pageNum: string,  pageSize: string  )

> UXUY 操作列表

```typescript
account.getAccountRecord(1,20)
```

| **Parameter** | **Type** | **Description** | **Default** |
| ------------- | -------- | --------------- | ----------- |
| pageNum       | string   | 当前页数            | 1           |
| pageSize      | string   | 列表数量            | 10          |



#### getRecordDetail(assetClaimId: string)

> UXUY 操作列表明细

```typescript
account.getRecordDetail({assetClaimId:''})
```

| **Parameter** | **Type** | **Description** | **Default** |
| ------------- | -------- | --------------- | ----------- |
| assetClaimId  | string   | 单个历史明细 Id       |             |
