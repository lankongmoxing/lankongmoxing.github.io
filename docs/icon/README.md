# icon

1. 主要使用于侧边栏导航、业务控件等

## 方式

- ant 提供的 矢量 icon <https://2x.antdv.com/components/icon-cn>

- ant 提供的自定义 createFromIconfontCN，本框架使用的方式

## 具体实现

1. 登录 iconfont.cn 账号

2. 选择需要的 icon 添加到**购物车**

3. 将购物车中的 icon 添加到**项目**，也可以上传svg文件到项目中

4. 进入 资源管理 -> 我的项目 -> 选择 **symbol** 生成代码

- ts 参考代码

```typescript
import { createFromIconfontCN } from "@ant-design/icons-vue";

const MyIcon = createFromIconfontCN({
  scriptUrl: "//at.alicdn.com/t/font_2379642_k23gr2d16ne.js", // 在 iconfont.cn 上生成
});

export default {
  components: {
    MyIcon,
  },
};
```

- hmlt 参考代码

```html
<my-icon :type="iconName" />
```

- tips

将远程的js文件放置到本地，方式因三方原因导致的资源访问问题

## 封装

敬请期待😄

## 更新时间

2021/02/26
