---
description: A little example of using uxlink-js-sdk
---

# Minimal Example

#### Connecting to UXAuth

```
By calling the login method we provide, you can quickly get the token, which currently supports WeChat and telegram 2 methods
```

#### 用微信登录授权

```typescript
// 
const { auth, interfaces } = new UXLINK();

// connectTo to wechat
await auth.connectTo(interfaces.LoginAuthType.wx, AppID, redirectUri, state);
```

{% hint style="info" %}
```
WeChat login will redirectUri will return the code, when we get the code, we can get the token required by UXLINK
```
{% endhint %}

```typescript
// getUrlCode("code");
const uxlinkToken = await auth.toWX(code);

const { account } = new UXLINK.init(uxlinkToken,apikey)
```

### Login with Telegram&#x20;

{% hint style="info" %}
<pre><code><strong>If you use the robot API to develop, please connect with the API we provide
</strong></code></pre>
{% endhint %}

coming soon
