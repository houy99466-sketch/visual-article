---
name: visual-article
description: Turn the current visible conversation context into a publishable visual article for WeChat Official Accounts plus a separate generated homepage hook image. Use when the user asks to summarize a conversation, project, product idea, collaboration process, or current context into an illustrated article, especially with WeChat-copyable HTML/rich text, HTML-built diagrams, flowcharts, scenario visuals, market problem framing, solution, advantages, concrete use case, future outlook, and a cover image. Always save every generated artifact under E:\codex produce in a new folder named after the specific project, feature, product, or function discussed in the context.
---

# Visual Article

## Core Behavior

Use the current visible conversation as the source material. Do not claim to read hidden or unavailable history. If the user specifies a starting point, use the visible content from that point onward. If details are incomplete, infer reasonable product, user, market, scenario, and value details from the available context and clearly shape them into a coherent article.

Treat `E:\codex produce` as the default storage root for this skill and its outputs. Store the real skill directory, generated HTML, generated images, project copies, repositories, substantial work artifacts, and any user-facing deliverables there by default. Do not create real deliverables, project folders, generated repositories, copied skill folders, article assets, or substantial artifacts on the C drive. A local Codex discovery path may contain only a junction or pointer to the E drive skill directory when required for Codex to find the skill.

Create these user-facing deliverables each time:

1. `wechat-article.html`: the primary deliverable, optimized so the visible article body can be copied into the WeChat Official Accounts editor as rich text.
2. `article.html`: an optional full-page preview version when useful.
3. `cover.png`: a separate generated image for the article homepage or push-card cover.

Save every run under `E:\codex produce\<specific-context-name>\`. Put the article and cover image inside that folder. The skill may be discovered through a local Codex skill path such as `C:\Users\<user>\.agents\skills\visual-article`, but that path must only be a junction or pointer. The real skill directory and all generated deliverables must stay under `E:\codex produce`.

## Required Workflow

1. Inspect the visible conversation and identify the project, product, feature, function, or work outcome.
2. Decide a clear article angle. Prefer practical value over a transcript-style summary.
3. Choose an output folder name from the specific thing being built or explained.
4. Build a compact content brief with:
   - 目标读者或目标用户
   - 市场问题或工作流困境
   - 解决方案
   - 核心优势
   - 上下文中出现的核心功能和生成产物
   - 实际价值、意义和工作流影响
   - 关键设计取舍或决策
   - 具体案例场景
   - 未来展望
   - 上下文中提到的 GitHub 或项目链接
   - 最适合解释内容的视觉模块
5. Read `references/article-structure.md` before drafting the article.
6. Read `references/visual-patterns.md` before creating article diagrams.
7. Read `references/wechat-format.md` before creating the primary article output.
8. Create `wechat-article.html` using WeChat-copyable rich-text HTML. Prefer inline styles, simple block layout, copyable visual blocks, and text-first diagrams. Avoid relying on global CSS, JavaScript, canvas, SVG, external stylesheets, remote images, or interactive behavior inside the copyable article body.
9. Optionally create `article.html` as a browser preview if it helps review the output, but do not make it the only article deliverable.
10. Read `references/cover-image-brief.md` before generating the homepage hook image.
11. Generate one separate cover image after the article is drafted. The cover must attract interest and must not merely repeat the article title.
12. Verify that `wechat-article.html` exists, opens as a standalone file, and contains a clearly marked copyable article body.

## Article Requirements

The article must include:

- A title derived from the context.
- Chinese section titles only, unless the user explicitly asks for another language.
- A short preface or summary, not overly long.
- A substantial section explaining what problem exists in the market or user workflow.
- A substantial section explaining the solution.
- A substantial section explaining the value, functions, meaning, and advantages.
- A core function breakdown based on the visible context.
- A focused example or scenario after the advantages. This is the main persuasive section.
- A section explaining key design choices or tradeoffs when the context contains them.
- A future outlook section after the example.
- A project address or related links section when GitHub or another public link appears in context.
- A concise ending.
- Multiple visuals built directly into the WeChat-copyable HTML, such as flow blocks, system maps, before/after comparisons, timelines, or scenario diagrams made from styled sections, tables, text labels, separators, and simple shapes.

When the context lacks complete facts, create plausible details that fit the demonstrated function and label the article as a product narrative rather than a factual case study. Do not invent specific external statistics, company claims, or user quotes unless the conversation provides them.

Default to a Chinese long-form article suitable for a WeChat Official Account. Market problem, solution, advantages, example, and future outlook are the minimum skeleton, not a limit. Expand the article by mining the visible context for concrete functionality, user value, workflow change, meaning, decisions, produced artifacts, publishing links, and what the work enables next. Unless the user asks for a short article, aim for at least 1800 Chinese characters when enough context exists.

## Output Rules

Use `E:\codex produce` for the skill folder and all generated deliverables. Treat this as the default storage root unless the user explicitly chooses another drive or path. For each skill run, create a new folder whose name directly matches the specific project, product, feature, or function in the conversation.

```text
E:\codex produce\智能日历\
  wechat-article.html
  article.html
  cover.png
```

Prefer human-meaningful names over generic skill names. For example:

- If the context is about an intelligent calendar, use `E:\codex produce\智能日历`.
- If the context is about a resume optimizer, use `E:\codex produce\简历优化器`.
- If the context is about a local knowledge assistant, use `E:\codex produce\本地知识助手`.

Do not name output folders after the skill or source plugin unless that is the actual project topic. Avoid generic names such as `visual-article`, `conversation-to-article`, `consulter-visual-article`, `article-output`, or `project-summary`.

When the folder name contains spaces, punctuation, or unsafe filename characters, simplify it into a clean Chinese or short kebab-case name while preserving the project meaning.

If a tool or application temporarily creates files on the C drive, move the user-facing result to `E:\codex produce` and clean up unnecessary temporary files when practical. Never leave the final output only on C.

Prefer filenames:

- `wechat-article.html`
- `article.html`
- `cover.png`

If multiple variants are produced, use suffixes such as `article-v2.html` or `cover-v2.png`.

## Resources

- Read `references/article-structure.md` for the required article narrative structure.
- Read `references/visual-patterns.md` for HTML-native diagram patterns.
- Read `references/wechat-format.md` for WeChat Official Accounts copy/paste formatting rules.
- Read `references/cover-image-brief.md` for homepage hook image rules.
- Use `assets/html-template.html` as a starting point when useful, adapting it freely to the current content.
- Use `assets/wechat-template.html` as the preferred starting point for `wechat-article.html`.
