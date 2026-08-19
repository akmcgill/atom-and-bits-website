# Content drafting — how this works

This folder is the **source of truth for page content**, kept separate from the finished HTML in `case-studies/`,
`index.html`, `about.html`, etc. You write or edit plain `.md` files here; Claude regenerates the real HTML page
from them whenever you want to see how it looks. Nothing about the visual design lives in these files — that's
entirely handled by the site's existing CSS, so what you see in the regenerated HTML is the actual, final look:
real card layout, real image cropping, real mobile behavior. No approximation.

## Where drafts live

1. **This folder, in the site repo** — the durable, version-controlled home. Commit and push `content/` the same
   way you already commit `case-studies/`. Git gives you full history on every draft: what changed, when, and you
   can always roll back.
2. **A backup copy in the claude.ai Project** ("Atom + Bits Website") — kept in sync as a second safety net,
   independent of whether you've pushed to git yet.
3. **Delivered to you directly** in conversation whenever a file is created or meaningfully updated.

Nothing should ever exist in only one place.

## File naming

One `.md` file per page, named to match its HTML counterpart:

```
content/case-studies/<slug>.md   →  case-studies/<slug>.html
content/about.md                 →  about.html
content/index.md                 →  index.html
```

## The format

Every case study follows the same skeleton — a few metadata lines at the top, then labeled sections in the order
they appear on the page. You don't need to write any HTML or worry about styling; just fill in the sections. The
block markers below (`[MEDIA: ...]`, `> CALLOUT`, etc.) are the only "syntax" to know — everything else is just
normal writing.

```markdown
---
title: The page's H1
where: Kroger · Manufacturing · Project MAKE   (the small teal label above the H1)
dek: The 1-2 sentence hook under the H1
role: Sr. Manager, Product & Program Management
timeline: Project MAKE · 2022-2025
team: Who was involved
focus: One line describing the thematic focus
metrics:
  - 100+ workflows mapped
  - 100+ interviews in 2 weeks
  - 8 product teams
---

# Key image
[MEDIA: landscape — description of what this image should show, for the placeholder tile and for whoever sources/shoots it later]
Caption: The caption text under the image.

# The problem
Normal paragraphs go here. Write as much as you need — this becomes the "problem" section body copy.

> CALLOUT (teal): Label for the callout
> The callout's body text. Use teal for context/definitions/notes, orange for a stronger flagged insight.

# What I did
Intro paragraph for this section, if needed.

## Artifact 1: Short title
Body text for the first numbered card in the 3-card grid.

## Artifact 2: Short title
Body text for the second card.

## Artifact 3: Short title
Body text for the third card.

[MEDIA: landscape — description]
Caption: Caption text.

[MEDIA-GRID]
[MEDIA: portrait — description]
> CALLOUT (orange): Label
> Body text — this pairs side-by-side with the media item above in a two-up layout.
[/MEDIA-GRID]

# Pull quote
> The quote text itself, first person or a direct quote from someone else.
— Attribution line (who said it, and when/where)

# Outcome
Closing paragraph on impact.

## Stat 1: 100+
Label describing what this number means.

## Stat 2: 2 weeks
Label.

## Stat 3: 8 product teams
Label.

# What's next in this series
(Optional — only for Project MAKE pages that reference the rest of the series.)
```

## Optional blocks (use only if the story needs them)

- **`[MAP-LIST]` / `[/MAP-LIST]`** — a bordered, row-based comparison list (used in the Kitchen ERP page for
  "decision → domain → insight"). Each row is a bold headline, a small teal label, and a body paragraph:
  ```
  ## Row: Row headline (the decision, stated plainly)
  DOMAIN: small teal label
  Body text — the insight this row is making.
  ```
  Known inconsistency to clean up: the discovery page (`project-make-discovery.html`) currently uses a slightly
  different visual variant of this component (two small labels instead of one bold headline + one label). Both
  render fine on their own pages since each page's CSS is self-contained, but they should be normalized to one
  version next time either page gets touched, so future markdown always maps to the same visual result.
- **`> MINI-QUOTE`** — a smaller second quote when a page already has one `# Pull quote` and needs a second voice
  (used in the go-live page). Same format as the pull quote block, just the `MINI-QUOTE` marker instead.
- **Two callouts in one section** are fine — just repeat the `> CALLOUT (...)` block.

## What NOT to worry about

- Exact HTML tags, classes, colors, fonts — all handled automatically from the section markers above.
- Image files — reference them in plain English inside `[MEDIA: ...]`; real filenames get wired up when actual
  images are ready. Until then the page shows the graceful placeholder tile, exactly like the live site does now.
- Formatting/typography — write like you're writing an email. Bold/italic (`**bold**`, `*italic*`) works if you
  want it, but isn't required.

## Files in this folder

- `case-studies/_template.md` — blank starting point, copy it to start a new case study.
- `case-studies/kitchen-erp.md` — a worked example, converted from the live, shipped `kitchen-erp.html` page, so
  you can compare the draft format side-by-side with the final result.
