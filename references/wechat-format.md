# WeChat Official Accounts Formatting

Use this reference when creating the primary `wechat-article.html` deliverable. The goal is a file that can be opened in a browser, selected from the article body, copied, and pasted into the WeChat Official Accounts editor with usable rich-text formatting.

## Core Rules

- Put the copyable article inside a clearly marked container near the top of the page.
- Use mostly inline styles on elements. Avoid depending on `<style>` classes for the article body because paste targets may strip class-based CSS.
- Avoid JavaScript, canvas, interactive elements, external CSS, web fonts, and remote images in the copyable article body.
- Avoid SVG in the copyable article body unless the user explicitly wants browser-only visuals. WeChat paste flows often do not preserve SVG reliably.
- Prefer simple tags: `<section>`, `<p>`, `<h1>`, `<h2>`, `<h3>`, `<strong>`, `<span>`, `<blockquote>`, `<hr>`, `<table>`, `<tbody>`, `<tr>`, `<td>`, `<ul>`, `<ol>`, `<li>`.
- Keep paragraphs short. WeChat readers scan vertically.
- Use inline `style` attributes for spacing, color, border, background, font size, and alignment.
- Keep the width fluid. Use `max-width: 680px; margin: 0 auto;` on the copyable container.

## Required File Shape

Create `wechat-article.html` with:

1. A small instruction strip outside the copyable body that says which area to copy.
2. A copyable article container with `id="wechat-copy-root"`.
3. The full article content inside that container.
4. No required external assets for the article body.

## Recommended Visual Blocks

### Highlight Summary

Use a soft background block:

```html
<section style="margin: 20px 0; padding: 18px; border-radius: 8px; background: #f5f7fb; border-left: 4px solid #2f6fed;">
  <p style="margin: 0; color: #334155; font-size: 16px; line-height: 1.8;">...</p>
</section>
```

### Flow Diagram

Use stacked steps:

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

### Before / After

Use a two-column table, which tends to paste better than CSS grid:

```html
<table style="width: 100%; border-collapse: separate; border-spacing: 8px; margin: 20px 0;">
  <tr>
    <td style="width: 50%; vertical-align: top; padding: 16px; border-radius: 8px; background: #fff7ed; border: 1px solid #fed7aa;">
      <strong>Before</strong>
      <p style="margin: 8px 0 0;">...</p>
    </td>
    <td style="width: 50%; vertical-align: top; padding: 16px; border-radius: 8px; background: #ecfdf5; border: 1px solid #a7f3d0;">
      <strong>After</strong>
      <p style="margin: 8px 0 0;">...</p>
    </td>
  </tr>
</table>
```

### Case Story Timeline

Use numbered blocks separated by vertical spacing:

```html
<section style="margin: 20px 0;">
  <section style="padding: 16px; margin-bottom: 10px; border-left: 4px solid #2f6fed; background: #ffffff;">
    <strong>1. 场景开始</strong>
    <p style="margin: 8px 0 0;">...</p>
  </section>
</section>
```

## Writing Rules

- Make the article readable even if some decorative styles are stripped.
- Use visual blocks to clarify structure, not to imitate a complex webpage.
- Avoid long code blocks in the WeChat article unless the user specifically needs them.
- Prefer Chinese section titles when the intended publishing channel is a Chinese WeChat Official Account.
- Keep the title and opening strong, but do not make the cover image repeat the title.
