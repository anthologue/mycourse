# Mini-Course: Java OOP for Beginners

A small static teaching site built once from 3 source slide images. Not a
tool for visitors to upload their own content — the lessons are fixed,
authored content derived from the slides the user provides in-session.

## Stack & Conventions

- **Stack**: Single static `index.html` file — HTML, CSS (`<style>`),
  and JS (`<script>`) all inline in one file. No build step, no
  framework, no backend. Section switching is client-side JS (show/hide
  `.lesson` elements), not separate pages.
- **Folder structure**:
  - `index.html` — the entire site: all lesson sections plus the
    stepper nav and switching logic
  - `assets/` — any images/diagrams reused from or inspired by the
    slides (only if/when needed — none used so far)
- **Content style**: each section is written as normal lesson prose
  (explanation, then example code, then a short recap) — not a
  slide-by-slide transcript. Java code samples use standard Java
  conventions (PascalCase classes, camelCase methods/vars) and should be
  short enough to read in one screen.
- **Navigation**: a top "stepper" nav lists all lessons and jumps to any
  of them; each lesson also has Prev/Next buttons at the bottom, driven
  by the same JS. Order matches the slide order.
- **No dependencies**: don't pull in CSS/JS frameworks unless asked —
  keep it readable, self-contained, and easy to open with just a browser
  (or a trivial static server).
- **Testing**: no automated tests for a static content site; verify by
  opening pages in a browser and checking links/navigation manually.
- **Visual design** (chosen from 3 mocked-up directions — "Modern
  Technical"):
  - Fonts: `IBM Plex Sans` (headings/body), `IBM Plex Mono` (code) via
    Google Fonts, `system-ui`/`Consolas` fallbacks.
  - Palette: light cool-gray background (`oklch(0.985 0.004 240)`),
    near-black cool text (`oklch(0.22 0.006 240)`), teal accent
    (`oklch(0.55 0.11 195)`), dark code blocks (`oklch(0.16 0.01 240)`
    bg) with soft-rounded corners (~6-10px).
  - Layout: top bar with course title + a horizontal numbered "stepper"
    nav across the 3 lessons (filled circle + teal underline for the
    current step); content column max-width ~720px, centered; recap in
    a tinted teal card; Prev/Next row at the bottom, Next styled as a
    solid teal button.

## Feature Plan

### Data model
No database — content lives directly in `index.html` as one `<section
class="lesson">` per topic. Shared structure per section: eyebrow
(page X/N), title, intro paragraph, one or more subheading+prose+code
blocks, recap card, prev/next nav row.

The 3 slides turned out to be one continuous topic (inheritance,
via a library "Member/Student/Staff" example) rather than 3 unrelated
topics, so the lessons are the 3 stages of that one example:

1. **The Problem** — why you'd want inheritance (naive duplicate
   `Student`/`Staff` classes)
2. **Superclass & Subclass** — pulling shared fields/methods into a
   `Member` superclass, `extends`
3. **Inheritance in Action** — what a subclass inherits automatically
   vs. what stays unique to it

### Phases

- [x] **Phase 1 — Confirm content source**: reviewed the 3 slide
  images (all one inheritance example, in 3 stages — see data model).
- [x] **Phase 2 — Scaffold site**: skipped separate scaffolding — built
  directly into Phase 3 since the site is one file.
- [x] **Phase 3 — Write lesson sections**: all 3 sections written into
  `index.html`, in slide order, matching the chosen visual design.
- [x] **Phase 4 — Wire navigation**: stepper nav + Prev/Next buttons
  wired via JS section show/hide.
- [ ] **Phase 5 — Review pass**: open in browser, click through all
  nav paths (stepper clicks, Prev/Next, first/last section states),
  proofread lesson content against the slides for accuracy.

Open question, still unresolved: whether to add a small practice
exercise/quiz per section beyond what's on the slides — not done yet,
current sections stick to expanding the slide content only.
