# HTML-Native Visual Patterns

Create article visuals directly in HTML. For the primary `wechat-article.html`, prioritize WeChat-copyable rich-text structures: styled sections with inline CSS, tables, callout blocks, numbered timelines, comparison panels, simple text arrows, and divider lines. Do not depend on remote images for body visuals.

Use inline SVG or canvas only in optional browser preview files such as `article.html`. Avoid SVG, canvas, JavaScript, and external CSS inside the copyable WeChat article body because WeChat editors may strip or fail to preserve them.

## Required Visual Mix

Include at least three different visual explanations. Prefer four or more when the article is substantial.

Good defaults:

- Problem map: shows fragmented inputs, manual steps, unclear outputs, or pain points.
- Solution flow: shows input -> analysis -> structure -> WeChat article -> cover image.
- Before/after comparison: shows the user state before and after the solution.
- Scenario timeline: shows a realistic user moving through the workflow.
- System architecture: shows reusable skill instructions, context analysis, HTML generation, and image generation.

## Visual Construction Rules

- Use semantic HTML around each visual with a short caption.
- For `wechat-article.html`, use inline styles on each element rather than depending on global CSS classes.
- Use tables or stacked `<section>` blocks for comparison boards, cards, and timelines.
- Use text arrows such as `→`, step numbers, border-left accents, and background panels instead of SVG arrows when targeting WeChat copy/paste.
- Use readable labels. Do not overcrowd diagrams.
- Keep colors varied and restrained; avoid making the whole article one hue.
- Make visuals narrow-screen friendly: stacked blocks should read well in a mobile-width WeChat editor.
- Use shapes, spacing, arrows, and hierarchy to explain the idea visually.

## Suggested Diagram Ideas

### Problem Map

Show several styled boxes or stacked callouts such as:

- Long conversation
- Unclear product angle
- Missing case story
- No publishable visuals
- Cover image repeats title

Connect them with text arrows or a central highlighted block named "publishing friction".

### Solution Flow

Show:

`visible context -> project understanding -> article structure -> HTML diagrams -> cover hook image -> publishable package`

### Before / After

Before:

- Manual summarizing
- Plain text output
- Weak visual explanation
- Repeated formatting work

After:

- Reusable skill
- Structured article
- Built-in diagrams
- Separate cover hook

### Scenario Timeline

Show a user starting with a messy discussion, invoking the skill, receiving an article folder, then using the HTML and cover image in a publishing workflow.
