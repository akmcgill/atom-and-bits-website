# Atom + Bits — Portfolio Site

Karina McGill's personal portfolio and case study site for Atom + Bits consulting.

**Live site:** https://akmcgill.github.io/atom-and-bits-website/

## Structure

```
index.html              Home page
about.html               About page
case-studies/            Case study index + individual case study pages
assets/                  Images, resume, headshot — organized by case study under assets/case-studies/
content/                 Markdown source content that mirrors the live case study pages
explorations/            Early design concepts, kept for reference
```

## Running locally

Static HTML, no build step or dependencies. Open any file directly in a browser, or serve the folder:

```
python3 -m http.server
```

Then visit http://localhost:8000

## Deployment

Hosted via GitHub Pages, deployed from the `main` branch root. Pushing to `main` publishes automatically, usually within a minute or two — check the repo's "Actions" tab to watch a deploy in progress.

See `SITE-README.md` for design system details (colors, type, layout conventions).
