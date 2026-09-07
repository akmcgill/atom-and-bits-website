# Atom + Bits — Portfolio Site

Karina McGill's personal portfolio and case study site for Atom + Bits consulting.

**Live site:** https://akmcgill.github.io/atom-and-bits-website/

## Structure

```
index.html              Home page
about.html               About page
case-studies/            Case study index + individual case study pages that are LIVE (linked from nav)
case-studies/drafts/     Case study pages that are built but not yet linked anywhere — safe to edit,
                         not reachable from the site. Move a file up into case-studies/ and add its
                         card/row to index.html, about.html, and case-studies/index.html to launch it.
assets/                  Images, resume, headshot — organized by case study under assets/case-studies/
content/                 Markdown source content that mirrors the live case study pages
explorations/            Early design concepts, kept for reference
```

## Workflow: shipping a case study

Everything on `main` is live the moment it's pushed (see Deployment below), so a case study only moves
from `case-studies/drafts/` into `case-studies/` — and gets a card/row added to the 3 nav-linked pages —
once it's actually ready to be public. Do in-progress edits on a branch if you want to keep `main` clean
while iterating; merge to `main` only when a page is ready to launch.

## Running locally

Static HTML, no build step or dependencies. Open any file directly in a browser, or serve the folder:

```
python3 -m http.server
```

Then visit http://localhost:8000

## Deployment

Hosted via GitHub Pages, deployed from the `main` branch root. Pushing to `main` publishes automatically, usually within a minute or two — check the repo's "Actions" tab to watch a deploy in progress.

See `SITE-README.md` for design system details (colors, type, layout conventions).
