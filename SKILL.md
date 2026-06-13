---
name: visual-article
description: Turn the current visible conversation context into a publishable visual HTML article plus a separate generated homepage hook image. Use when the user asks to summarize a conversation, project, product idea, collaboration process, or current context into an illustrated article, especially with HTML-built diagrams, flowcharts, scenario visuals, market problem framing, solution, advantages, concrete use case, future outlook, and a cover image. Always save the skill's outputs under E:\codex produce in a newly named folder based on the context's project or function.
---

# Visual Article

## Core Behavior

Use the current visible conversation as the source material. Do not claim to read hidden or unavailable history. If the user specifies a starting point, use the visible content from that point onward. If details are incomplete, infer reasonable product, user, market, scenario, and value details from the available context and clearly shape them into a coherent article.

Create two user-facing deliverables each time:

1. A self-contained HTML article with embedded CSS and HTML-native visuals.
2. A separate generated image for the article homepage or push-card cover.

Save every run under `E:\codex produce\<context-based-folder-name>\`. Name the folder from the current context's project, feature, or topic using lowercase words, digits, and hyphens when practical. Put the article and cover image inside that folder.

## Required Workflow

1. Inspect the visible conversation and identify the project, product, feature, or work outcome.
2. Decide a clear article angle. Prefer practical value over a transcript-style summary.
3. Build a compact content brief with:
   - Target reader or user
   - Market problem
   - Proposed solution
   - Key advantages
   - Concrete example scenario
   - Future outlook
   - Best visual explanations
4. Read `references/article-structure.md` before drafting the article.
5. Read `references/visual-patterns.md` before creating article diagrams.
6. Create a self-contained `article.html` using HTML, CSS, and inline SVG or CSS-built diagrams. Avoid remote image dependencies for article body visuals.
7. Read `references/cover-image-brief.md` before generating the homepage hook image.
8. Generate one separate cover image after the article is drafted. The cover must attract interest and must not merely repeat the article title.
9. Verify that the output files exist and that the HTML opens as a standalone file.

## Article Requirements

The article must include:

- A title derived from the context.
- A short preface or summary, not overly long.
- A section explaining what problem exists in the market or user workflow.
- A section explaining the solution.
- A section explaining advantages.
- A focused example or scenario after the advantages. This is the main persuasive section.
- A future outlook section after the example.
- A concise ending.
- Multiple visuals built directly into the HTML, such as flowcharts, system maps, before/after comparisons, timelines, or scenario diagrams.

When the context lacks complete facts, create plausible details that fit the demonstrated function and label the article as a product narrative rather than a factual case study. Do not invent specific external statistics, company claims, or user quotes unless the conversation provides them.

## Output Rules

Use `E:\codex produce` for the skill folder and all generated deliverables. For each skill run, create a new folder such as:

```text
E:\codex produce\visual-article-automation\
  article.html
  cover.png
```

Prefer filenames:

- `article.html`
- `cover.png`

If multiple variants are produced, use suffixes such as `article-v2.html` or `cover-v2.png`.

## Resources

- Read `references/article-structure.md` for the required article narrative structure.
- Read `references/visual-patterns.md` for HTML-native diagram patterns.
- Read `references/cover-image-brief.md` for homepage hook image rules.
- Use `assets/html-template.html` as a starting point when useful, adapting it freely to the current content.
