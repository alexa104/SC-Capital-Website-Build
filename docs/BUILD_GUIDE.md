# Build Guide: Replicating the Homepage Mockup

Work top to bottom on a **duplicated** Squarespace 7.1 site (Core plan —
gives full access to Custom CSS and Code Injection), isolated from the
live domain until you deliberately migrate the finished result over.

## 1 · Site-Wide Setup

Colors and fonts apply across the whole site — set these first. See
`docs/BRAND.md` for the full color table, font choices, and logo
instructions (**Design > Colors**, **Design > Fonts**, **Design > Logo**).

## 2 · Header & Navigation

- Upload the logo exactly as-is (see `docs/BRAND.md`); target height
  ~88–92px; tighten header vertical padding to ~8px so the taller logo
  doesn't push the nav bar height up too much.
- Header background = the logo's own cream background (`#FCF5EA`) in
  **Design > Header** — keep this fixed in both light and dark mode (see
  the Step 4 CSS callout below).
- No separate text wordmark — the logo lockup carries the name on its own.
- Primary nav: **About, Who We Serve, Services, Insights, Contact**.
- Add **Family Login** as a secondary/utility nav item if your template
  has that slot; otherwise place it last in the main nav.

## 3 · Homepage Sections, In Order

Build these top to bottom — full copy and layout notes for each are in
`content/homepage.md`. **The order you actually use determines the
section-position numbers in Steps 4, 5, and 7**, so keep track as you go
(see `docs/SITEMAP.md` for the assumed order).

1. Hero
2. Who We Serve
3. Services
4. Approach & Philosophy
5. The SC Capital Difference
6. Positioning Strip
7. Our Expertise
8. Insights
9. Closing CTA ("Submit an RFP")

Plus four **separate pages** (not homepage sections — no position number,
not linked in main nav), built as their own Squarespace Pages once the
homepage buttons that link to them exist:

- **For Families** (`content/pages/for-families.md`)
- **For Family Offices** (`content/pages/for-family-offices.md`)
- **How We Work With You** (`content/pages/how-we-work-with-you.md`)
- **Our Team** (`content/pages/our-team.md`)

And the **footer** plus three **legal pages** (Disclaimer, Privacy Policy,
Terms of Use) — see the end of `content/homepage.md` for footer copy and
`content/pages/legal.md` for the legal text (note the entity-name edit
that needs counsel sign-off before publishing).

## 4 · Custom CSS

**Design > Custom CSS** — paste `squarespace/custom-css.css` in full. The
`nth-of-type` section numbers in it assume the Step 3 build order above —
if yours differs, update the numbers to match (see Step 7 below).

> **Dark-band fix:** the rules targeting section 5 (The SC Capital
> Difference) and section 9 (closing RFP band) hardcode both background
> and text color rather than using the theme-linked ink token. A dark
> section that pulls its background from the same token used for text
> elsewhere on the page will break the moment dark mode flips that token
> to a light value — hardcoding both sides avoids it entirely.

## 5 · Code Injection

**Settings > Advanced > Code Injection > Footer** — paste
`squarespace/code-injection-footer.html` in full. This tags blocks in the
sections listed in its `revealSections` array for scroll-reveal, cycles
the animated word in Who We Serve, and adds the light/dark toggle button.

The `revealSections` array lists every section (1–9) — trim it down if
you'd rather leave some sections static. Confirm the actual numbers
against your build in Step 7.

## 6 · Light / Dark Toggle

Already included in `squarespace/custom-css.css` and
`squarespace/code-injection-footer.html` — nothing extra to add. Three
things worth knowing:

- **Honest limitation:** the toggle only affects elements styled through
  the `--sc-*` custom properties. Squarespace's own section-level theme
  system (the native "bright/dark" setting on each section) is separate
  and won't automatically follow this toggle — full sitewide dark mode
  would need each section's native theme checked individually once live.
  Treat this as a strong starting point, not a guaranteed one-shot fix.
- **Header stays fixed on purpose:** its background, border, and nav link
  colors use hardcoded hex values, not theme tokens, so the header looks
  consistent in both modes and never clashes with the logo (used
  unmodified, designed against a light ground).
- **Dark sections stay fixed too:** The SC Capital Difference and the
  closing RFP band are hardcoded dark green, deliberately not tied to
  `--sc-ink` — see the Step 4 callout above.

## 7 · Finding Section Position Numbers

Both the CSS and the Code Injection script target sections by position,
counting from the top starting at 1. Based on the assumed build order:

| # | Section |
|---|---|
| 1 | Hero |
| 2 | Who We Serve |
| 3 | Services |
| 4 | Approach & Philosophy |
| 5 | The SC Capital Difference |
| 6 | Positioning Strip |
| 7 | Our Expertise |
| 8 | Insights |
| 9 | Closing CTA ("Submit an RFP") |

If a number doesn't match, the effect will show up on the wrong section —
correct the number everywhere it appears (CSS and Code Injection), save,
and refresh. None of the four separate pages are in this list — they're
separate pages, not homepage sections (see Step 3).

## 8 · Preview & Publish

- [ ] Check both desktop and mobile preview toggles
- [ ] Confirm the hero overlay, Services card accents, and Approach &
      Philosophy decorative elements all landed on the correct sections
- [ ] Confirm blocks fade in on scroll where expected, and the Who We
      Serve word cycles correctly
- [ ] Click the light/dark toggle and check both states — specifically
      confirm The SC Capital Difference and the closing RFP band stay
      dark green with light, legible text in **both** modes
- [ ] Confirm the header stays the same cream color, and the logo reads
      clearly, in both light and dark mode
- [ ] Confirm the RFP form card is legible (dark text on its light card,
      not light-on-light or light-on-dark) and that a test submission
      actually reaches you; confirm the single-card Our Expertise section
      reads correctly
- [ ] Review the footer disclaimer and contact details for accuracy
- [ ] Once satisfied, migrate the finished Custom CSS, Code Injection, and
      section content over to the real live site in one deliberate pass
