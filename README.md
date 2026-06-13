# visual-article

`visual-article` is a Codex skill for turning the current visible conversation context into a publishable WeChat-ready visual article and a separate homepage hook image.

It is designed for conversations where a project, feature, product idea, workflow, or collaboration process needs to become a clear article rather than a raw summary.

## What It Produces

The real skill directory and all generated outputs are intended to live under:

```text
E:\codex produce
```

Codex may use a local discovery junction such as `C:\Users\<user>\.agents\skills\visual-article`, but that path should only point to the E drive directory. Real skill files, generated HTML, images, repositories, project copies, and substantial artifacts should not be stored on the C drive by default.

Each run creates a new context-based folder under that E drive root.

The folder name should match the specific project, product, feature, or function discussed in the context. For example, if the conversation is about building an intelligent calendar, the output folder should be named `智能日历`, not `visual-article` or `consulter-visual-article`.

The default output files are:

```text
wechat-article.html
article.html
cover.png
```

`wechat-article.html` is the primary article deliverable. Open it in a browser and copy the marked article body into the WeChat Official Accounts editor as rich text. It uses inline styles, short sections, callout blocks, tables, and text-first diagrams instead of relying on global CSS, JavaScript, SVG, or canvas. `article.html` can still be generated as a browser preview when useful. The cover image is generated separately as a hook image for a homepage, feed card, or push entry.

## Article Structure

The skill asks Codex to produce an article with:

- A short preface or summary
- Chinese-only section titles by default
- A more developed discussion of the market or workflow problem
- The proposed solution
- A fuller explanation of value, functions, meaning, and advantages
- A core function breakdown based on the visible context
- A concrete example scenario
- Key design choices or tradeoffs when the context supports them
- A future outlook section
- A project address or GitHub link section when links appear in context
- A concise closing
- Multiple WeChat-copyable HTML visuals such as flow blocks, system maps, timelines, and before/after comparisons

If the conversation does not provide every detail, the skill instructs Codex to infer plausible product, user, and scenario details from the visible context while avoiding unsupported external claims.

## Usage

Invoke the skill explicitly:

```text
Use $visual-article to turn the current context into a visual article and homepage hook image.
```

You can also specify a visible starting point:

```text
Use $visual-article from the message where I started describing the publishing workflow.
```

## Repository Contents

```text
SKILL.md
agents/openai.yaml
references/article-structure.md
references/visual-patterns.md
references/wechat-format.md
references/cover-image-brief.md
assets/html-template.html
assets/wechat-template.html
```

## Notes

The skill only uses the conversation content visible to the current Codex context. It does not claim to read hidden, unavailable, or external chat history.
