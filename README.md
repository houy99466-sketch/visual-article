# visual-article

`visual-article` is a Codex skill for turning the current visible conversation context into a publishable visual HTML article and a separate homepage hook image.

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
article.html
cover.png
```

The HTML article is self-contained and uses HTML, CSS, inline SVG, or canvas for article-body visuals. The cover image is generated separately as a hook image for a homepage, feed card, or push entry.

## Article Structure

The skill asks Codex to produce an article with:

- A short preface or summary
- The market or workflow problem
- The proposed solution
- The advantages
- A concrete example scenario
- A future outlook section
- A concise closing
- Multiple HTML-native visuals such as flowcharts, system maps, timelines, and before/after comparisons

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
references/cover-image-brief.md
assets/html-template.html
```

## Notes

The skill only uses the conversation content visible to the current Codex context. It does not claim to read hidden, unavailable, or external chat history.
