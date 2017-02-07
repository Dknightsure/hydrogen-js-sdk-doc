# 内容渲染

---

用户在 BAAS 后台创建内容后，后台会显示该内容的 ID ，用户根据此 ID 通过接口获取经过处理后的、适合微信小程序展示的数据

```
ifanr.bass.getContent({ // content/:id/
  id: contentID
});
```

用户在小程序代码里粘贴指定的 wxml 和 wxss 代码片段（wxml、wxss 从 SDK 文档获取），然后在 JS 代码里通过 API 获取指定 ID 的内容，并把返回的数据赋给 wxml 绑定的相应变量完成渲染。
如果是一些特殊内容，比如与购物有关的内容可能会有一些默认的商品信息和状态信息。
示例:

```
<view bind="xxx" class="c1">
  <view wx-for="item in list" class="c2">
    <text class="c3">{{ item }}</text>
  </view>
  <view bind="c4">
  </view>
</view>

// 相应的原生富文本为：
<div class="c1">
  <ul class="c2">
    <li class="c3">aaa</li>
    <li class="c3">aaa</li>
  </ul>
  <div class="c4">
  </div>
</div>
```

保证 wxml 与 js 代码绑定变量的命名统一：用户自己保证，baas 后台提供相应文档提示。

