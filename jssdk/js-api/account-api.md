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

#### updateUserInfo(userName: string, userAvatar: string, userGender: number)

> #### 更新用户个人信息

```typescript
account.updateUserInfo('username', 'userAvatar', 0)
```

| **Parameter** | **Type** | **Description**          | **Default** |
| ------------- | -------- | ------------------------ | ----------- |
| userName      | string   | 字段长度不得超过 130 个字符，支持特殊字符  |             |
| userAvatar    | string   | 目前只支持IPFS，CDN资源，未来支持 NFT |             |
| userGender    | Number   | <p>0: <br>1：<br>2</p>    | 0           |
|               |          |                          |             |

####

编辑个人用户信息



获取个人的好友列表



获取个人资产（UXUY）



Claim UXUY Token



Claim UXUY 历史列表



UXUY 历史详情
