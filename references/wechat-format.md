# 微信公众号排版

创建主交付物 `wechat-article.html` 时使用本参考。目标是生成一个可以在浏览器中打开、选中正文区域、复制并粘贴到微信公众号编辑器中的富文本文章。

## 核心规则

- 把可复制正文放在页面靠前、标记清楚的容器中。
- 正文元素尽量使用内联样式。不要依赖 `<style>` 里的 class，因为粘贴到编辑器时 class 样式可能被过滤。
- 可复制正文中避免 JavaScript、canvas、交互元素、外部 CSS、网页字体和远程图片。
- 可复制正文中尽量避免 SVG，除非用户明确要浏览器预览效果。微信公众号粘贴流程不一定稳定保留 SVG。
- 优先使用简单标签：`<section>`、`<p>`、`<h1>`、`<h2>`、`<h3>`、`<strong>`、`<span>`、`<blockquote>`、`<hr>`、`<table>`、`<tbody>`、`<tr>`、`<td>`、`<ul>`、`<ol>`、`<li>`。
- 段落要短，适合手机端纵向阅读。
- 使用内联 `style` 控制间距、颜色、边框、背景、字号和对齐。
- 宽度保持流式布局。可复制容器建议使用 `max-width: 680px; margin: 0 auto;`。

## 文件结构要求

创建 `wechat-article.html` 时包含：

1. 可复制正文之外放一个简短提示条，说明应该复制哪个区域。
2. 可复制正文容器使用 `id="wechat-copy-root"`。
3. 完整文章正文放在这个容器内。
4. 正文不依赖外部资源。

## 推荐视觉模块

### 重点概要

使用柔和背景块：

```html
<section style="margin: 20px 0; padding: 18px; border-radius: 8px; background: #f5f7fb; border-left: 4px solid #2f6fed;">
  <p style="margin: 0; color: #334155; font-size: 16px; line-height: 1.8;">...</p>
</section>
```

### 流程图

使用纵向步骤块：

```html
<section style="margin: 24px 0;">
  <section style="padding: 14px 16px; border: 1px solid #d9dee7; border-radius: 8px; background: #ffffff;">
    <strong style="color: #2f6fed;">01 输入</strong>
    <p style="margin: 8px 0 0; color: #475467;">...</p>
  </section>
  <p style="text-align: center; color: #98a2b3; margin: 8px 0;">↓</p>
  <section style="padding: 14px 16px; border: 1px solid #d9dee7; border-radius: 8px; background: #ffffff;">
    <strong style="color: #20866f;">02 分析</strong>
    <p style="margin: 8px 0 0; color: #475467;">...</p>
  </section>
</section>
```

### 前后对比

使用双列表格，通常比 CSS grid 更适合粘贴：

```html
<table style="width: 100%; border-collapse: separate; border-spacing: 8px; margin: 20px 0;">
  <tr>
    <td style="width: 50%; vertical-align: top; padding: 16px; border-radius: 8px; background: #fff7ed; border: 1px solid #fed7aa;">
      <strong>使用前</strong>
      <p style="margin: 8px 0 0;">...</p>
    </td>
    <td style="width: 50%; vertical-align: top; padding: 16px; border-radius: 8px; background: #ecfdf5; border: 1px solid #a7f3d0;">
      <strong>使用后</strong>
      <p style="margin: 8px 0 0;">...</p>
    </td>
  </tr>
</table>
```

### 案例时间线

使用编号模块和纵向间距：

```html
<section style="margin: 20px 0;">
  <section style="padding: 16px; margin-bottom: 10px; border-left: 4px solid #2f6fed; background: #ffffff;">
    <strong>1. 场景开始</strong>
    <p style="margin: 8px 0 0;">...</p>
  </section>
</section>
```

## 写作规则

- 即使部分装饰样式被过滤，文章也必须仍然可读。
- 视觉模块用于帮助理解结构，不要模仿复杂网页。
- 除非用户明确需要，否则不要在微信公众号文章中放很长的代码块。
- 面向微信公众号时，默认使用中文标题和中文小标题。
- 标题和开头要有吸引力，但封面图不要复读标题。
