# Mini-Course: Java OOP for Beginners

A small static teaching site built once from 3 source slide images. Not a
tool for visitors to upload their own content — the lessons are fixed,
authored content derived from the slides the user provides in-session.

## Stack & Conventions

- **Stack**: Plain static HTML/CSS/JS. No build step, no framework, no
  backend — this is 3-5 pages of prose content with simple navigation.
- **Folder structure**:
  - `index.html` — landing page listing the lessons
  - `lessons/01-<slug>.html`, `lessons/02-<slug>.html`, ... — one file per
    section
  - `css/style.css` — shared styles
  - `assets/` — any images/diagrams reused from or inspired by the slides
- **Naming**: lesson files are zero-padded and slugged from the topic
  (e.g. `01-classes-and-objects.html`). Keep slugs short and lowercase.
- **Content style**: each section is written as normal lesson prose
  (explanation, then example code, then a short recap) — not a
  slide-by-slide transcript. Java code samples use standard Java
  conventions (PascalCase classes, camelCase methods/vars) and should be
  short enough to read in one screen.
- **Navigation**: every lesson page has Prev/Next links plus a link back
  to the index. Navigation order matches the slide order.
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
No database — content lives directly in the HTML files, one per lesson.
Shared structure per lesson page: title, intro paragraph, body sections
(explanation + code sample), recap/summary, prev/next nav.

### Phases

- [ ] **Phase 1 — Confirm content source**: user shares the 3 slide
  images in-session; review each one and note its topic/key points before
  writing prose.
- [ ] **Phase 2 — Scaffold site**: create folder structure, base
  `css/style.css`, and `index.html` shell listing 3 lessons (titles TBD
  from slide review).
- [ ] **Phase 3 — Write lesson sections**: convert each slide into one
  lesson HTML page (prose + code example + recap), in slide order.
- [ ] **Phase 4 — Wire navigation**: add Prev/Next links across all
  lessons and link them from the index.
- [ ] **Phase 5 — Review pass**: open in browser, check all links work,
  proofread lesson content against slides for accuracy.

Open question to confirm with user before/while building: whether each
section should include a small practice exercise/quiz beyond what's on
the slides, or stick strictly to expanding the slide content.
