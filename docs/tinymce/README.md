# tinymce 富文本编辑器

1. 引入 tinymce vue 版本，即 @tinymce/tinymce-vue
2. 下载需要的语言包，默认英文

## js 部分

```typescript
import { defineComponent } from "vue";
import Editor from "@tinymce/tinymce-vue";

export default defineComponent({
  components: {
    Editor,
  },
  computed: {
    tinymceContent: {
      get(): String {
        return this.content;
      },
      set(newValue: String) {
        this.$emit("input", newValue);
      },
    },
  },
  data() {
    return {
      init: {
        selector: "#mytextarea",
        language_url: "./tinymic/langs/zh_CN.js",
        language: "zh_CN",
        skin_url: "./tinymic/skins/",
        plugins: plugins,
        toolbar: toolbar,
        height: "500",
      },
    };
  },
});
```

## html 部分

```html
<Editor
  id="mytextarea"
  v-model="tinymceContent"
  :init="init"
  :disabled="disabled"
  @onClick="onClick"
>
</Editor>
```

## css 部分

```css
/* 隐藏 tinymce 提示弹窗 */
.tox-notifications-container {
  display: none !important;
}
```

## tips

1. 语言包和 skins 文件放置在 public 文件中保证路径以及编译
2. 没有apikey的情况需要用css隐藏提示。如果有则不需要，在html添加上对应的appkey
3. [tinymce-vue github](https://github.com/tinymce/tinymce-vue)