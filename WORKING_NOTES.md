# Working Notes — Allison (Allie) Krier Personal Landing Page

> **Internal document — not intended for public audiences.**
> This file is for developer and AI assistant reference only. It should be read before every working session and updated at the end of every session before closing.

---

## How to Use This File (For AI Assistants)

1. Read this entire file before suggesting any changes or writing any code.
2. Read `README.md` for the public-facing project description, feature list, and setup instructions.
3. Do not change the folder structure or file naming conventions without discussing it first.
4. Follow all conventions listed in the **Conventions** section exactly — do not introduce new patterns without asking.
5. Do not suggest any approach listed in **What Was Tried and Rejected**.
6. Ask clarifying questions before making large structural changes (e.g., adding a framework, splitting into multiple HTML pages, or restructuring the CSS).
7. This project was AI-assisted (initial structure and stylesheet generated with Claude via Replit). Refactor conservatively — prefer targeted edits over rewrites.

---

## Current State

**Last Updated:** 2026-03-25

The landing page is fully built and serving correctly in the Replit development environment. All required sections from the PRD are implemented. The page is responsive, accessible to WCAG 2.2 Level AA, and deployable as a static site. README.md and WORKING_NOTES.md are complete.

### What Is Working
- [x] Sticky navy navigation bar with anchor links to all sections
- [x] Hero section — circular headshot, name, tagline, "Get in Touch" and "See My Work" CTA buttons
- [x] About Me section — three-paragraph bio in first-person, direct tone
- [x] Skills section — two grouped categories with pill-badge tags (Data & Analytics / Business & Productivity)
- [x] Projects section — three cards in a two-column responsive grid (Titanic, Target, Port Washington Bank)
- [x] Experience section — two-column date/content layout with bullet points from resume
- [x] Contact section — email, LinkedIn, and GitHub icon badges opening in new tabs
- [x] Footer — navy background with name and location
- [x] Fully responsive layout from 320px to desktop
- [x] Headshot loading from `images/allkrier_headshot.png`
- [x] Google Fonts (Inter) loaded via CDN
- [x] All external links use `target="_blank" rel="noopener noreferrer"`
- [x] Semantic HTML5 structure throughout (`<header>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<nav>`)
- [x] No inline styles — all CSS in `css/stylesheet.css`
- [x] README.md complete
- [x] WORKING_NOTES.md complete

### What Is Partially Built
- [ ] **Projects — Titanic Data Analysis:** Description is written based on PRD context, but no link to a GitHub repo or PDF exists yet. Needs a real project link when available.
- [ ] **Projects — Target Merchandising Case Competition:** Description is written based on PRD context only. Actual outcome, team size, and placement are unknown — needs real details.
- [ ] **`js/scripts.js`:** File exists but is empty — reserved for future use.

### What Is Not Started
- [ ] LICENSE file (MIT) — needs to be added to the GitHub repo
- [ ] Mobile browser testing on Safari iOS and Chrome Android
- [ ] Analytics or visitor tracking (out of scope per PRD)
- [ ] Resume download button (out of scope per PRD, and resume should not be embedded per STANDARDS.md)

---

## Current Task

**What I was working on when I last stopped:**
All primary build work is complete. The last tasks finished were generating `README.md` (all 16 sections) and `WORKING_NOTES.md`. The page is live in the Replit dev environment, all PRD-required sections are implemented, and deployment configuration has been set to static site.

**The very next step is:**
Add the MIT `LICENSE` file to the GitHub repository (go to repo → Add file → Create new file → name it `LICENSE` → use GitHub's license template chooser to select MIT).

---

## Architecture and Tech Stack

| Technology | Version | Why It Was Chosen |
|---|---|---|
| HTML5 | Current standard | Required by STANDARDS.md; semantic elements throughout |
| CSS3 | Current standard | Required by STANDARDS.md; no framework option was chosen in STANDARDS.md, so vanilla CSS was used |
| Google Fonts — Inter | Latest | Clean, modern sans-serif that reads well at small sizes; fits the "professional, approachable" tone in STANDARDS.md |
| Python `http.server` | Built-in (Python 3) | Zero-dependency local dev server for serving the static files in Replit; no build step required |
| shields.io | N/A (CDN) | Badge generation for README.md |

---

## Project Structure Notes

```
3300-landing-page-2/
├── index.html              # Single HTML file — all page sections live here
├── css/
│   └── stylesheet.css      # All styles — no inline styles anywhere
├── images/
│   └── allkrier_headshot.png  # Headshot — referenced as images/allkrier_headshot.png
├── js/
│   └── scripts.js          # Empty — reserved, do not delete
├── PRD.md                  # Product requirements — read before adding/removing sections
├── STANDARDS.md            # Technical and design rules — read before changing CSS or HTML patterns
├── README.md               # Public-facing project documentation
└── WORKING_NOTES.md        # This file
```

- **`css/stylesheet.css`** uses CSS custom properties (`:root` block at the top) for all colors, fonts, spacing, and max-widths. Always edit design tokens there first rather than changing values inline throughout the file.
- **`js/scripts.js`** must not be deleted — it is referenced in STANDARDS.md's folder structure spec and may be needed later.
- **`images/`** — the headshot filename and path are hardcoded in `index.html`. If the file is renamed, the `src` attribute in the hero `<img>` tag must be updated.
- **`PRD.md` and `STANDARDS.md`** must not be modified without the owner's direction — they are the source of truth for what to build and how to build it.

---

## Data / Database

This project has no persistent data, database, or back-end. It is a fully static site. All content is hardcoded in `index.html`. There are no API calls, no form submissions, and no server-side processing.

---

## Conventions

### Naming Conventions
- HTML file: `index.html` (lowercase, in root)
- CSS file: `css/stylesheet.css` (lowercase, in `css/` subfolder)
- JS file: `js/scripts.js` (lowercase, in `js/` subfolder)
- Images: lowercase with underscores — e.g., `allkrier_headshot.png`
- CSS class names: BEM-inspired kebab-case — e.g., `.site-header`, `.hero-photo`, `.card-header`, `.btn--primary`
- CSS custom properties: `--color-*`, `--font-*`, `--text-*`, `--max-width-*`, `--shadow-*`, `--radius-*`

### Code Style Rules
- No inline `style=""` attributes anywhere in HTML
- No `<style>` tags in HTML files
- All external links must include `target="_blank" rel="noopener noreferrer"`
- All `<img>` elements must have descriptive `alt` attributes
- Heading hierarchy must be maintained: `<h1>` (one per page) → `<h2>` (section headings) → `<h3>` (card/item headings)
- Section headings (`<h2>`) use accent teal color (`--color-accent`)
- Card/item headings (`<h3>`) use navy color (`--color-navy`)

### CSS Patterns
- All design tokens are CSS custom properties defined in `:root` at the top of `stylesheet.css`
- Responsive breakpoints: `max-width: 640px` for tablet/mobile, `max-width: 400px` for small mobile
- Layout uses CSS Grid for skills, projects, and experience sections
- Hover states use `transform: translateY(-2px)` + `box-shadow` increase on cards — do not change this pattern without discussion
- Buttons use modifier classes: `.btn--primary` and `.btn--outline`

### Git Commit Message Style
- Imperative sentence, no period: `Add contact section icon badges`
- Prefix with area if helpful: `CSS: Increase card hover shadow`, `HTML: Add NRF experience item`

---

## Decisions and Tradeoffs

- **Vanilla CSS, no framework:** STANDARDS.md listed Bootstrap 5.3 and Tailwind as options but the framework field was not filled in. Vanilla CSS was chosen because the project is a single static page with no interactive components, making a framework unnecessary overhead. Do not suggest adding Bootstrap or Tailwind.
- **Single `index.html` file:** STANDARDS.md explicitly requires a single `index.html` in the root. Do not suggest splitting into multiple pages.
- **Navy + teal + white color palette:** STANDARDS.md left the hex values as placeholders but specified "Navy / teal / white. Clean and modern, not flashy." The palette (`#1B2A4A`, `#0D6E6E`, `#F8F9FA`, `#E9ECEF`, `#212529`) was derived from that guidance. Do not suggest changing the palette without owner direction.
- **Inter for both headings and body:** STANDARDS.md left the font field blank. Inter was chosen because it is a highly legible, professional sans-serif with excellent screen rendering at the sizes used. Do not suggest swapping fonts without owner direction.
- **Projects section: third card spans full grid width:** The PRD requires three projects. A two-column grid with the third card spanning both columns avoids an awkward half-empty row and gives the bank experience card more reading room since it has the most detail.
- **No JavaScript on the page:** The site is purely static per STANDARDS.md. Smooth scrolling is handled via `scroll-behavior: smooth` in CSS. Do not add JS for any behavior that CSS can handle.
- **Headshot path hardcoded as `images/allkrier_headshot.png`:** The PRD and STANDARDS.md specify the image lives in `/images`. The filename matches the actual file in the repo. Do not change this path.

---

## What Was Tried and Rejected

- **Bootstrap 5.3 via CDN:** Considered because it was listed in STANDARDS.md as an option, but rejected in favor of vanilla CSS to keep the project simple, lightweight, and fully within the student's control. Do not suggest Bootstrap.
- **Separating experience into its own standalone timeline component with JS:** Considered using a JS-animated timeline for the Experience section, but STANDARDS.md specifies no JavaScript. The two-column CSS Grid layout achieves the same visual clarity. Do not suggest a JS timeline.
- **Embedding the resume PDF:** Considered adding a "Download Resume" button, but STANDARDS.md explicitly states: "Do not link to or embed my resume anywhere on the site." Do not suggest this.

---

## Known Issues and Workarounds

- **Titanic project and Target case competition descriptions are approximated:** The PRD lists both as "Must" items but the resume PDF does not contain detail for either. The descriptions were written based on the PRD's brief labels ("SQL, Excel" and "Retail Strategy"). **Workaround:** Placeholder descriptions are in place that are directionally accurate. They must be updated with real details when the owner provides them. Do not remove or shorten these descriptions in the meantime.
- **`js/scripts.js` is empty:** The file exists to satisfy STANDARDS.md's required folder structure. It has no content. **Workaround:** File is present but blank. Do not delete it.

---

## Browser / Environment Compatibility

| Browser | Status |
|---|---|
| Chrome (desktop) | Confirmed working — tested in Replit preview |
| Firefox (desktop) | Expected to work — no CSS features used that Firefox doesn't support |
| Safari (desktop) | Expected to work — standard HTML5/CSS3 only |
| Chrome (Android) | Not yet tested |
| Safari (iOS) | Not yet tested |

**Environment:** Replit (NixOS, channel `stable-25_05`). Static files served by `python3 -m http.server 5000` in development. Production deployment configured as a static site (no build step, `publicDir: "."`).

---

## Open Questions

- What are the actual details of the Titanic Data Analysis project — was it a class assignment, a self-directed project, or something else? Does a GitHub repo or report exist that can be linked?
- What was the outcome of the Target Merchandising Case Competition — did the team place? What was the specific recommendation?
- Should the hero tagline be updated to include a specific role title (e.g., "Aspiring Retail Data Analyst") once a target job title is clearer?
- Should a "Coursework" or "Education" subsection be added to highlight relevant BAIS courses for recruiters who want to verify technical depth?
- Is a downloadable resume button in-scope for a future version, or should it remain out of scope?

---

## Session Log

### 2026-03-25
- Explored repository structure (single `index.html` with "Hello World", no CSS, no framework)
- Read `PRD.md`, `STANDARDS.md`, and extracted resume content from `allison-krier resume (1-3) (2).pdf`
- Built complete `index.html` with all six PRD-required sections: Hero, About, Skills, Projects, Experience, Contact
- Built complete `css/stylesheet.css` with CSS custom properties, responsive grid layout, accessibility compliance, and sticky navigation
- Confirmed page renders correctly in Replit preview with headshot loading
- Created `README.md` with all 16 required sections
- Created `WORKING_NOTES.md` (this file)
- Configured Replit deployment as static site (`publicDir: "."`)
- Left incomplete: LICENSE file (must be added on GitHub), mobile browser testing, real project details for Titanic and Target sections
- Decisions made: vanilla CSS (no framework), single-page layout, navy/teal/white palette, Inter font
- Next step: add MIT LICENSE file to GitHub repo

---

## Useful References

- [MDN HTML5 Semantic Elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Element) — reference for correct semantic tag usage
- [MDN CSS Custom Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties) — reference for `:root` token pattern used in this project
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/) — used to verify the teal/white and navy/white contrast ratios meet WCAG 2.2 Level AA (4.5:1 normal text, 3:1 large text)
- [Google Fonts — Inter](https://fonts.google.com/specimen/Inter) — font loaded via CDN in `<head>`
- [CSS Grid Guide — CSS Tricks](https://css-tricks.com/snippets/css/complete-guide-grid/) — reference for the skills, projects, and experience grid layouts
- [shields.io](https://shields.io) — badge URL builder for README
- **AI assistance:** Initial `index.html` and `css/stylesheet.css` generated by Claude (Anthropic) via Replit based on `PRD.md`, `STANDARDS.md`, and resume content. All content reviewed and approved by the author. Subsequent documentation (`README.md`, `WORKING_NOTES.md`) also AI-generated and reviewed by the author.
