# 登录

---
##登录授权

示例：
```
ifanr.bass.login({
  code: xxx
});
```

走 session/authenticate/ 接口

使用 wx.login 返回的 code 去 SSO 获取 access token，并把 token 存到本地，以后每次发送 API 请求时，带上 Authorization：token 请求头

##退出登录
```
ifanr.bass.logout();
```
走 session/destroy/ 接口



