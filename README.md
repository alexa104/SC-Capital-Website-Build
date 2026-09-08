# SC Capital — Squarespace Website Build

This repo holds the content and code for rebuilding the SC Capital, LLC homepage
and supporting pages on Squarespace (7.1, Core plan), based on an approved
mockup and build guide from an earlier session.

Squarespace itself is a closed, web-based site builder — there's no git deploy
or API for building pages, so this repo is the staging ground: drafted copy,
sitemap, and ready-to-paste Custom CSS / Code Injection. You copy the content
and code from here into the Squarespace dashboard by hand.

## What's here

- **`docs/BUILD_GUIDE.md`** — step-by-step instructions for rebuilding the
  mockup on a duplicated Squarespace site. Start here.
- **`docs/BRAND.md`** — color tokens and fonts (Design > Colors / Fonts).
- **`docs/SITEMAP.md`** — every page, its slug, and whether it's in the main
  nav.
- **`content/homepage.md`** — every homepage section in build order, with
  exact copy to paste into Squarespace's native content blocks.
- **`content/pages/`** — copy for the four separate pages (For Families, For
  Family Offices, How We Work With You, Our Team) plus the legal pages.
- **`squarespace/custom-css.css`** — the full stylesheet for
  **Design > Custom CSS**, combining site-wide styling, section accents, the
  light/dark toggle, and the separate-page layouts (family blocks,
  engagement cards, team grid).
- **`squarespace/code-injection-footer.html`** — the full script for
  **Settings > Advanced > Code Injection > Footer**: scroll-reveal, the
  "Who We Serve" word-cycle, and the dark mode toggle button.

## Working assumption

Build on a **duplicated** Squarespace site, isolated from the live domain,
per the build guide's status note. Migrate the finished Custom CSS, Code
Injection, and section content to the live site in one deliberate pass once
everything checks out (see Step 8 in the build guide).

## Firm details (for reference)

- **SC Capital, LLC** — Saint Petersburg, Florida
- Founder: Stephen Collins (CFA, CAIA, CIMA)
- Contact: stephen@sccapitalllc.com · (843) 303-3331
