---
description: A little example of using uxuy-js-sdk
---

# Minimal Example

#### Connecting to UXUYAuth

```
By calling the login method we provide, you can quickly get the token, which currently supports WeChat and telegram 2 methods
```

#### 用微信登录授权

```typescript
// 
const { auth, interfaces } = new UYUX();

// connectTo to wechat
await auth.connectTo(interfaces.LoginAuthType.wx, AppID, redirectUri, state);
```

{% hint style="info" %}
```
WeChat login will redirectUri will return the code, when we get the code, we can get the token required by UXUY
```
{% endhint %}

```typescript
// getUrlCode("code");
const uxuyToken = await auth.toWX(code);

const { account } = new UXUY.init(uxuyToken,apikey)
```

### Login with Telegram&#x20;

{% hint style="info" %}
<pre><code><strong>If you use the robot API to develop, please connect with the API we provide
</strong></code></pre>
{% endhint %}

coming soon
