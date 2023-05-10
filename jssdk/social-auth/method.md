---
description: A little example of using uxuy-js-sdk
---

# Minimal Example

#### Connecting to UXUYAuth

通过调用我们提供的登录方式，就可以快速获取到token，目前支持微信和 telegram 2中方式

#### 用微信登录授权

```typescript
// 
const { auth, interfaces } = new UYUX();

// connectTo to wechat
await auth.connectTo(interfaces.LoginAuthType.wx, AppID, redirectUri, state);
```

{% hint style="info" %}
微信登录会redirectUri 会返回 code，当我们获取到 code 的时候，则能获取到 UXUY 需要的token
{% endhint %}

```typescript
// getUrlCode("code");
const uxuyToken = await auth.toWX(code);

const { account } = new UXUY.init(uxuyToken,apikey)
```

### 使用 Telegram 登录

{% hint style="info" %}
如果你使用机器人API 开发，请对接我们提供的 API
{% endhint %}

