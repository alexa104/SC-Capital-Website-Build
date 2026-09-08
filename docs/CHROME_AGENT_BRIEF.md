# SC Capital — Squarespace Build Brief (Single-Shot Brief for Claude in Chrome)

You are picking up a website build with no other context — everything you
need is in this one document. Read it fully before acting.

## Scope & guardrails — read this first

- **Only work on this site:** `https://helicon-grey-ab5r.squarespace.com/config/`
  This is a **duplicate** of a live production site, created deliberately so
  changes here are safe. **Never navigate to, log into, or modify the live
  SC Capital site or any other domain.** If you're ever unsure whether
  you're on the duplicate, check the address bar for `helicon-grey-ab5r` —
  if it's not there, stop.
- Work through the steps below **in order** — later CSS and JavaScript
  target homepage sections by numeric position, which depends on the
  section build order in Step 3.
- After each major step (site-wide setup, header, each homepage section,
  each separate page, CSS paste, code injection paste), briefly pause and
  let the person you're working with glance at it before continuing, since
  visual judgment calls (card widths, image crops) are easier for them to
  confirm than to get right blind.
- Squarespace's Fluid Engine editor changes fairly often — if a menu path
  below doesn't match what you see, use Squarespace's search/help within
  the dashboard to find the current equivalent rather than guessing.

---

## Step 1 · Site-Wide Setup

Colors and fonts apply across the whole site — set these first, before any section content, in **Design > Colors** and **Design > Fonts**.

Set these first in Squarespace (**Design > Colors** / **Design > Fonts**) —
every homepage section and separate page depends on them.

## Colors

| Token | Hex | Use |
|---|---|---|
| Ink (Sage) | `#4F6B62` | Headings, primary text |
| Ink Muted | `#7B988F` | Body copy |
| Line | `#E3D9C6` | Dividers, hairlines |
| Gold | `#D2A636` | Accents, primary buttons |
| Terracotta (Ember) | `#E18C6B` | Eyebrows, card accents, CTAs |
| Teal Accent | `#7B988F` | Card accent, secondary hover |
| Sand | `#E0C29E` | Card accent |
| Seafoam | `#B7DDD5` | Secondary accent |
| Paper (Cream) | `#FCF5EA` | Page background |
| Band (Dark Sections) | `#4F6B62` | Fixed dark background — hardcoded, not theme-linked (see the dark-band callout in the build guide's Custom CSS step) |

### Dark mode variants

| Token | Hex |
|---|---|
| Ink | `#F3ECDD` |
| Ink Muted | `#B7CBC3` |
| Line | `#37473F` |
| Gold | `#E3B94A` |
| Ember | `#E89A7A` |
| Teal | `#8FB0A6` |
| Sand | `#C9AD87` |
| Body background | `#1D2B27` |

## Fonts

Both are on Squarespace's native Google Fonts picker — no upload or
licensing needed.

- **Headings:** Playfair Display — high-contrast serif matching the wordmark
- **Body:** Montserrat — clean, letter-spaced sans, matches the tagline
  treatment

## Logo

Upload the logo file **exactly as-is, unmodified** in **Design > Logo** —
the full circular lockup with the "SC CAPITAL" wordmark and tagline, not a
cropped icon. Don't recolor, crop, or remove its background. Display height
~88–92px. No separate text wordmark next to it — the lockup carries the
name on its own.

---

## Step 2 · Header & Navigation

- Upload the logo exactly as-is (see the Logo section above); target
  display height ~88–92px; tighten header vertical padding to ~8px so the
  taller logo doesn't push the nav bar height up too much.
- Header background = the logo's own cream background (`#FCF5EA`) in
  **Design > Header** — keep this fixed in both light and dark mode (the
  Custom CSS in Step 4 hardcodes this rather than using a theme token).
- No separate text wordmark — the logo lockup carries the name on its own.
- Primary nav: **About, Who We Serve, Services, Insights, Contact**.
- Add **Family Login** as a secondary/utility nav item if the template has
  that slot; otherwise place it last in the main nav.

---

## Step 3 · Homepage Sections, In Order

Build these top to bottom in the page editor. **This exact order matters** — the Custom CSS and Code Injection in Steps 4–5 target sections by position (1 = Hero, 2 = Who We Serve, etc.).

Build these sections top to bottom in Squarespace's page editor. The order
here is what the Custom CSS and Code Injection scripts target by position
(section 1 = Hero, etc. — see `docs/SITEMAP.md`).

Set brand colors/fonts first (`docs/BRAND.md`) and the header/nav
(`docs/SITEMAP.md`) before starting on sections.

---

## 1 · Hero

Full-bleed nautical/coastal background photo with a dark sage→terracotta
gradient overlay (overlay CSS is in `squarespace/custom-css.css`). No
eyebrow label above the headline. Two buttons: a gold primary button to
Contact, and a ghost button to Approach & Philosophy. A trimmed aside line
in the lower right — no descriptive paragraph.

**Headline:** OCIO Services for Family Office and the Next Generation of Wealth

**Subhead:** We provide highly customized, institutional-caliber investment
solutions for complex, sophisticated Family Offices, UHNW Individuals and
Families, and the entrepreneurs and rising generation defining what's
next — independent, conflict-free, and built on 24 years of institutional
experience.

**Buttons:** "Start a Conversation" (primary, gold, links to `#contact`) ·
"See Our Approach" (ghost, links to `#about`)

**Aside (bottom right):** "Saint Petersburg, Florida" label, then
"SC Capital, LLC"

---

## 2 · Who We Serve

Heading includes an animated word that cycles through audience segments
(handled by the word-cycle script in
`squarespace/code-injection-footer.html`):

> Built for *[families]* writing the next chapter.

Wrap the cycling word in a `<span id="sc-word-cycle">families</span>` —
either a Code Block, or a span with that id inside the native heading block.

**Lead-in:** From next-generation wealth creators to established family
offices, we build long-term partnerships across every stage of the wealth
journey:

**List** (one line per segment, no numbering):
- Next Generation & Rising Generation Wealth Creators
- Entrepreneurs, Founders, Creators & Innovators
- Family Businesses, Enterprises & Executives
- Family Offices — Single and Multi-Family
- Private Equity & Venture Capital Partners
- Pro Athletes, Entertainment, Media & Influencers
- Women Entrepreneurs, Executives & Founders

**Buttons below the list, side by side:** "For Families →" (links to the
separate `/for-families` page) · "For Family Offices →" (links to
`/for-family-offices`)

---

## 3 · Services

*(Renamed from "What We Offer")* — visually differentiated with a heavier
terracotta top border on the section and a colored top-accent per card
(terracotta, gold, teal — see `squarespace/custom-css.css`), not a flat
background tint.

**Heading:** With 24+ years of experience, we provide the guidance you need
at every stage of your financial journey.

**Lead-in:** Customized concierge, white-glove services and solutions:

3-column card grid. No separate OCIO card — folded into Investment
Advisory & Management. The middle card has noticeably less content than
its neighbors — in the Fluid Engine editor, drag it narrower and widen the
other two (roughly 1.1 : 0.8 : 1.1) so its longer bullet phrases wrap
across more lines and close the height gap.

**Card 1 — Investment Advisory & Management**
Lead line: **OCIO Services** — full outsourced Chief Investment Officer
services, plus:
- Asset Allocation
- Due Diligence
- Optimization & Performance Reporting
- Strategy & Policy
- Risk Management
- Originating & Structuring Investments
- Investments Across All Asset Classes

**Card 2 — Family Office Formation & Structuring**
Lead line: End-to-end setup and structuring for new or evolving family
offices:
- Design & Implementation
- Legal & Operational Foundation, Leadership and Structure
- Strategic Direction, Execution & Planning

**Card 3 — Family Governance**
- Family Constitution
- Board Formation, Development, Membership & Oversight
- Investment Committee Formation
- Wealth & Family Communication & Dynamics
- Human Capital and Leadership Development & Training
- Next Generation, Rising Generation & Family Transition Advisory,
  Education, Planning and Sustainability

**Button below the grid:** "Portfolio Management Services →" links to the
separate `/how-we-work-with-you` page.

---

## 4 · Approach & Philosophy

2-column layout, differentiated with a heavy gold top border on the
section (not a background overlay). Left column reads as a pull-quote
with a gold left border.

**Heading:** Contrarian conviction. Patient capital.

**Left (pull-quote):** Our capital is permanent — flexible, patient, and
long term. We pursue long-duration compounded growth and outsized
absolute returns by focusing on:
- Capital appreciation, significant wealth generation, and long-term value
  creation
- The fundamentals, discount to intrinsic value, and market dislocations
- Downside protection to minimize risk at every stage

**Right:** We operate on a set of core principles that guide every client
relationship and investment decision:
- Alignment, Independence and Transparency
- Collaboration, Trust and a Family-Centric Partnership Approach
- Fiduciary, Stewardship, Service and Support
- Unbiased, Customized, Objective and No Conflicts of Interest
- Contrarian and Deep Value Investment Philosophy
- Disciplined with an Opportunistic Approach

---

## 5 · The SC Capital Difference

Section background is the **fixed dark sage** (`#4F6B62`, hardcoded — see
the dark-band callout in `squarespace/custom-css.css`; do not tie this to
the theme's ink token, or it'll invert and go illegible in dark mode).

**Heading:** The *edge* of independence. (italicize "edge")

4-column grid, each card top-bordered in its own accent color, lifts
slightly on hover, and fades in with a staggered delay as you scroll to it:

| Card | Copy |
|---|---|
| Cost & Overhead Reduction | Institutional oversight without the fixed cost of an in-house team. |
| Access & Deal Flow | Unparalleled access to a network of global expertise and specialists. |
| Independence, By Structure | Open-architecture. No proprietary products. One mandate: your outcomes. |
| Continuity | No key-person risk — institutional continuity across generations. |

---

## 6 · Positioning Strip

4-column layout, one stat per column. Sits **after** The SC Capital
Difference and right before Our Expertise — not directly under the hero.

- **24+ Years** — Family Office, Investment Advisory & Private Equity
- **$12B+** — In family capital under advisement
- **20–25** — Family office & UHNW relationships
- **Independent** — Open-architecture, conflict-free

---

## 7 · Our Expertise

*(Formerly "Our Story")* — differentiated with a heavy teal top border. A
large portrait-orientation headshot of Stephen (roughly 4:5) next to a
single condensed paragraph, followed by one centered card with name, role,
and credentials only (no career-timeline bullets).

**Eyebrow:** Our Expertise
**Heading:** Built from experience.

**Paragraph (next to headshot):** SC Capital was founded in 2024 by
Stephen Collins, capping a 24-year journey across four family offices as a
C-level investment executive who has lived the complexity our clients
face, not just advised on it — building a firm around institutional
discipline, delivered without institutional bureaucracy. A College of
Charleston graduate (magna cum laude, Finance & Political Science)
nominated three times to the U.S. Naval Academy and a nationally ranked
junior and ATP Tour tennis professional before turning to finance, Stephen
brings the same discipline and competitiveness to every client
relationship. A fourth-generation member of a Carolinas finance and retail
family — descended from the Collins Department Stores chain his
great-grandfather founded in 1903 — and an avid traveler across five
continents, he brings a global, contrarian perspective shaped by a
lifetime of firsthand experience.

**Card:** Stephen Collins — Founder, Managing Partner & Chief Executive
Officer · 24+ years — Family Office, Investment Advisory, Private Equity ·
CFA, CAIA, CIMA.

**Button below the card:** "Meet the Team →" links to the separate
`/team` page.

---

## 8 · Insights

Differentiated with a heavy sand top border. Text next to an email signup
form (no "Coming Soon" label):

**Copy:** Market commentary, research, and perspective for families
navigating what's next. Join our newsletter.

Email input field + "Subscribe" button (gold, primary style). Use
Squarespace's native Newsletter Block/Mailchimp integration if you want it
to actually collect emails, or a simple form block otherwise.

---

## 9 · Closing CTA — "Submit an RFP"

Same fixed dark sage background as The SC Capital Difference (hardcoded,
same reasoning). Centered content:

**Eyebrow:** Submit an RFP
**Heading:** Alignment | Family | Stewardship | Trust (no supporting line
beneath it)

A Squarespace **Form Block** styled as a light card floating on the dark
background (CSS in `squarespace/custom-css.css`), not a plain link/button.

**Fields:** First Name, Last Name, Email, Phone (optional), Family Office /
Firm Name (optional), "Tell Us About Your Needs" message box.

**Submit button:** "Submit RFP" — gold, primary style.

Wire the Form Block's storage/notification settings (Squarespace's native
form backend, or a Mailchimp/CRM connection) so submissions actually reach
you.

---

## Footer

**Firm**
SC Capital, LLC
Saint Petersburg, Florida

**Contact**
Stephen Collins, Founder & CEO
(843) 303-3331
stephen@sccapitalllc.com

**Site** — About · Who We Serve · Services · Insights · Family Login

**Legal** — Disclaimer · Privacy Policy · Terms of Use · LinkedIn (new tab:
`https://www.linkedin.com/company/sc-capital-llc-sc-capital-holdings-llc-scc/`)

**Legal disclaimer line:** This website is for informational purposes only
and does not constitute an offer to sell or a solicitation to buy any
securities, and does not constitute investment, legal, or tax advice. For
qualified investors only. © 2026 SC Capital, LLC. All rights reserved.

---

## Step 3b · Separate Pages

These four pages are **not** homepage sections — they don't get a position number and aren't part of the Step 4/5 CSS/JS targeting. Build them as their own Squarespace Pages (**Pages > add a page**), after the homepage buttons linking to them exist. None are in the main nav.

### Page: For Families

**Slug:** `/for-families` · **Not in main nav** — reached via the
"For Families →" button on the homepage's Who We Serve section.

Structure follows PermCap's families page (permcap.com/families) as a
framework only — three stacked, full-width blocks (not equal-width cards,
since each category's content runs a very different length). Copy below is
SC Capital's own, pulled from Services and Who We Serve, not new material.

## Header

Shared dark `.page-hero` treatment (see `squarespace/custom-css.css`) — a
Code Block with a "← Back to Home" link, eyebrow, heading, and lead-in.

**Eyebrow:** For Families
**Heading:** Every family's journey is different.
**Lead-in:** We adapt our approach to fit your family's unique needs —
three ways we can tailor our services:

## Block 1 — Family Office Investment Services

For families who want institutional-caliber investment management — asset
allocation, manager selection, and portfolio construction — delivered on
its own, without the overhead of standing up a full family office.

**Our Approach In Practice** (same 8 bullets as the homepage's Investment
Advisory & Management card):
- OCIO Services
- Asset Allocation
- Due Diligence
- Optimization & Performance Reporting
- Strategy & Policy
- Risk Management
- Originating & Structuring Investments
- Investments Across All Asset Classes

## Block 2 — Family Office Personal Services

For families who want support beyond the portfolio — governance,
communication across generations, education and preparation for the next
generation, and coordination of the people and structures around your
wealth.

**Our Approach In Practice** (combines Family Office Formation &
Structuring with Family Governance — 9 bullets):
- Design & Implementation
- Legal & Operational Foundation, Leadership and Structure
- Strategic Direction, Execution & Planning
- Family Constitution
- Board Formation, Development, Membership & Oversight
- Investment Committee Formation
- Wealth & Family Communication & Dynamics
- Human Capital and Leadership Development & Training
- Next Generation, Rising Generation & Family Transition Advisory,
  Education, Planning and Sustainability

## Block 3 — Individuals

For individuals — entrepreneurs, executives, and next-generation wealth
creators — who want the same institutional rigor and personal attention as
our family clients, scaled to what you need today.

**Who This Serves** (4 bullets pulled from Who We Serve):
- Next Generation & Rising Generation Wealth Creators
- Entrepreneurs, Founders, Creators & Innovators
- Pro Athletes, Entertainment, Media & Influencers
- Women Entrepreneurs, Executives & Founders

## Layout notes

Three Code Blocks stacked vertically, each with a colored top border
rotating gold → terracotta → teal (`.family-service-block` in
`squarespace/custom-css.css`, which also defines the `.offer-list`
dot-marker bullet style used here since this page uses Code Blocks rather
than native text blocks).

Below the three blocks: a "Portfolio Management Services →" button linking
to `/how-we-work-with-you`. End the page with a "Submit an RFP" button
linking to `/#contact`.

### Page: For Family Offices

**Slug:** `/for-family-offices` · **Not in main nav** — reached via the
"For Family Offices →" button on the homepage's Who We Serve section.

## Header

Shared dark `.page-hero` treatment (see `squarespace/custom-css.css`) — a
Code Block with a "← Back to Home" link, eyebrow, heading, and lead-in.

**Eyebrow:** For Family Offices
**Heading:** A true extension of your team.
**Lead-in:** Family offices carry unique demands — coordinating
investments, governance, philanthropy, and multigenerational goals under
one roof.

## Body

Single plain text block — no card grid needed, this page covers one
audience.

We work alongside your existing team and advisors as a true extension of
your office, providing OCIO-caliber investment management, tax-aware
planning, and institutional infrastructure without adding institutional
bureaucracy.

## Layout notes

End the page with a "Submit an RFP" button linking to `/#contact`.

### Page: How We Work With You

**Slug:** `/how-we-work-with-you` · **Not in main nav** — reached via the
"Portfolio Management Services →" button on the homepage's Services
section and on the For Families page.

Framing inspired by how Cambridge Associates' About page structures its
"Portfolio Management Services" section around engagement models rather
than practice areas — written in SC Capital's own voice, not copied text.

## Header

Shared dark `.page-hero` treatment (see `squarespace/custom-css.css`) — a
Code Block with a "← Back to Home" link, eyebrow, heading, and lead-in.

**Eyebrow:** How We Work With You
**Heading:** Built around how you want to work.
**Lead-in:** Every client relationship starts differently — some want full
delegation, others want a true partner alongside their own team. Three
ways we work together:

## Card 1 — Discretionary / OCIO

**Label:** Discretionary / OCIO
**Heading:** Your Fully Resourced Investment Office

For clients who want to delegate investment decision-making entirely, we
serve as your outsourced Chief Investment Officer — responsible for
strategy, implementation, day-to-day management, and operations, so your
time stays focused on your family or your business.

## Card 2 — Advisory Services

**Label:** Advisory Services
**Heading:** A Partner to Your Existing Team

For clients with in-house investment staff, or who want to stay closely
involved in every decision, we complement your team with manager access,
asset allocation guidance, and portfolio construction support.

## Card 3 — Asset Class Mandates

**Label:** Asset Class Mandates
**Heading:** Specialized Expertise, Where You Need It

For clients seeking focused expertise in a specific area — private equity,
hedge funds, real assets, private credit, co-investments, or secondaries —
we manage targeted mandates on a discretionary or non-discretionary basis,
alongside your broader portfolio.

## Layout notes

Three Code Blocks side by side, wrapping each in
`<div class="engagement-card">` — gold, terracotta, then teal top borders
in that order (`.engagement-grid` / `.engagement-card` in
`squarespace/custom-css.css`). End the page with a "Submit an RFP" button
linking to `/#contact`.

### Page: Our Team

**Slug:** `/team` · **Not in main nav** — reached via the "Meet the Team →"
button on the homepage's Our Expertise section.

Inspired by BowPoint's team page (bowpoint.com/team) — a dark hero band
with a stat-counter row, followed by a photo-card grid — adapted to
SC Capital's sage/gold palette, reusing SC Capital's own stats, not copied
text or imagery.

## Header (hero)

Full-width Code Block with the shared dark `.page-hero` background (see
`squarespace/custom-css.css`) — a "← Back to Home" link, eyebrow, heading,
lead-in, and (only on this page) the stat row below it.

**Eyebrow:** Our Team
**Heading:** Institutional experience, built around your family.
**Lead-in:** The people responsible for sourcing, structuring, and
stewarding every relationship we take on.

**Stat row** (`.team-stats` — reuses the homepage Positioning Strip
numbers):
- 24+ Years — Family Office, Investment Advisory & Private Equity
- $12B+ In Family Capital Under Advisement
- 20–25 Family Office & UHNW Relationships

## Leadership (5 cards)

| Name | Role | Notes |
|---|---|---|
| Stephen Collins | Founder, Managing Partner & Chief Executive Officer | CFA, CAIA, CIMA — real headshot, same one used in Our Expertise |
| Rob Johnson | Partner, Head of Sports, Entertainment & Media | Placeholder initials "RJ" until a headshot is supplied |
| — | Partner, Head of Technology & Venture Capital | Open-role card, "We're Hiring" |
| — | Director, Private Investments | Open-role card, "We're Hiring" |
| — | Analyst / Associate | Open-role card, "We're Hiring" |

## Team (7 cards, own "Team" eyebrow heading below Leadership)

| Name | Role |
|---|---|
| Georgia Gatti | Investment Associate |
| Ellie Assenmacher | Family Office & Investment Analyst |
| Alexa Gonzalez | Family Office Associate |
| Kendall Lagana | Marketing & Social Media Associate |
| Ava Frontino | Business Development, Family Engagement & Relationships Associate |
| Anastasia Zagoriy | Business Development, Family Engagement & Relationships Associate |
| — (open role) | We're Hiring — Investment Analyst |

Placeholder initials for anyone without a headshot yet; open-role cards use
a dashed-border placeholder instead (no gradient/initials), so they read as
unfilled rather than as a real person whose photo just hasn't been added
(`.team-photo--open` vs. `.team-photo--placeholder` in
`squarespace/custom-css.css`). Add more cards in the same `.team-card`
format as the team grows, and swap an open-role card for a real one once
that hire is made — `.team-grid` reflows automatically.

## Layout notes

Below the hero: a plain section with a card grid — one Code Block or
Image + Text block per person. End the page with a "Submit an RFP" button
linking to `/#contact`.

---

## Step 4 · Custom CSS

Go to **Design > Custom CSS** and paste the entire block below (replacing nothing that's already there is fine to check first, but this is meant to be the full stylesheet for this build).

```css
/* ============================================================
   SC Capital — Design > Custom CSS
   Paste this in full. Section-position numbers (nth-of-type)
   assume the homepage build order in content/homepage.md:
     1 Hero · 2 Who We Serve · 3 Services · 4 Approach & Philosophy
     5 The SC Capital Difference · 6 Positioning Strip
     7 Our Expertise · 8 Insights · 9 Closing CTA
   If your actual order differs, update the numbers below to match
   (see docs/SITEMAP.md).
   ============================================================ */

/* ---- Brand tokens ---- */
:root {
  --sc-ink: #4F6B62;
  --sc-ink-muted: #7B988F;
  --sc-line: #E3D9C6;
  --sc-gold: #D2A636;
  --sc-ember: #E18C6B;
  --sc-teal: #7B988F;
  --sc-sand: #E0C29E;
}

/* ---- Sticky header — fixed light-mode colors, not theme
     tokens, so the header always matches the logo's own
     background and stays consistent in both light and dark mode ---- */
#header {
  background: #FCF5EA;
  border-bottom: 1px solid #E3D9C6;
}
/* Nav link text — also fixed, same reasoning as the header
   background above. #header a is broad on purpose; if it also
   catches the logo link or a header button on your template,
   narrow it to the real nav-link class (Inspect Element on your
   live header to find it, e.g. .header-nav-item a). */
#header a { color: #4F6B62; }
#header a:hover { color: #E18C6B; }

/* ---- Hero = section 1: dark gradient overlay on the photo ---- */
.page-section:nth-of-type(1) {
  position: relative;
  overflow: hidden;
}
.page-section:nth-of-type(1)::before {
  content: '';
  position: absolute;
  inset: 0;
  z-index: 1;
  pointer-events: none;
  background: linear-gradient(
    160deg,
    rgba(79, 107, 98, 0.55) 0%,
    rgba(225, 140, 107, 0.28) 55%,
    rgba(79, 107, 98, 0.60) 100%
  );
}

/* ---- Services = section 3: heavier top border + colored
     card accents, replacing a flat background tint ---- */
.page-section:nth-of-type(3) {
  border-top: 3px solid var(--sc-ember);
}
.page-section:nth-of-type(3) .fe-block:nth-of-type(1) { border-top: 3px solid var(--sc-ember); }
.page-section:nth-of-type(3) .fe-block:nth-of-type(2) { border-top: 3px solid var(--sc-gold); }
.page-section:nth-of-type(3) .fe-block:nth-of-type(3) { border-top: 3px solid var(--sc-teal); }

/* ---- Approach & Philosophy = section 4: differentiated the
     same way as Services (section 3) — a heavy top border in a
     distinct accent color, not a background overlay ---- */
.page-section:nth-of-type(4) {
  border-top: 3px solid var(--sc-gold);
  border-bottom: 1px solid var(--sc-line);
}

/* ---- The SC Capital Difference = section 5: colored top-accent
     per card, hover lift, and a staggered fade-in — this replaces
     the "Compare to an In-House CIO" link as the section's visual
     interest. Assumes one .fe-block per card; if your layout uses
     a single block for the whole 4-up grid, target its child
     elements instead. ---- */
.page-section:nth-of-type(5) .fe-block {
  padding-top: 20px;
  transition: opacity .6s ease var(--sc-delay, 0s), transform .35s ease, box-shadow .25s ease;
}
.page-section:nth-of-type(5) .fe-block:nth-of-type(1) { border-top: 2px solid var(--sc-gold); --sc-delay: .05s; }
.page-section:nth-of-type(5) .fe-block:nth-of-type(2) { border-top: 2px solid var(--sc-ember); --sc-delay: .15s; }
.page-section:nth-of-type(5) .fe-block:nth-of-type(3) { border-top: 2px solid #B7DDD5; --sc-delay: .25s; }
.page-section:nth-of-type(5) .fe-block:nth-of-type(4) { border-top: 2px solid var(--sc-sand); --sc-delay: .35s; }
.page-section:nth-of-type(5) .fe-block:hover {
  transform: translateY(-4px);
  box-shadow: 0 10px 24px rgba(0, 0, 0, 0.28);
}
@media (prefers-reduced-motion: reduce) {
  .page-section:nth-of-type(5) .fe-block:hover { transform: none; }
}

/* ---- The SC Capital Difference = section 5, and the closing
     "Submit an RFP" band = section 9: FIXED dark background,
     not the theme-linked --sc-ink token. If you point a dark
     section's text at --sc-ink and its background at --sc-ink
     too, the dark-mode override below flips --sc-ink to a
     light color and the text becomes illegible against its own
     background. Hardcode both sides of this pairing instead. ---- */
.page-section:nth-of-type(5),
.page-section:nth-of-type(9) {
  background: #4F6B62 !important;
}
.page-section:nth-of-type(5) *,
.page-section:nth-of-type(9) * {
  color: #FCF5EA;
}
.page-section:nth-of-type(5) h1, .page-section:nth-of-type(5) h2, .page-section:nth-of-type(5) h3,
.page-section:nth-of-type(9) h1, .page-section:nth-of-type(9) h2, .page-section:nth-of-type(9) h3 {
  color: #FCF5EA !important;
}

/* ---- Section 9's Form Block sits on its own light card, not
     directly on the dark green — restore normal (dark) text
     inside it, since the "* { color: #FCF5EA }" rule above would
     otherwise make the form's own labels and typed text
     illegible against the light card. .sqs-block-form is
     Squarespace's real class for a Form Block; inspect your
     actual markup (right-click > Inspect) if your template
     wraps it differently. ---- */
.page-section:nth-of-type(9) .sqs-block-form,
.page-section:nth-of-type(9) .sqs-block-form * {
  color: var(--sc-ink) !important;
}
.page-section:nth-of-type(9) .sqs-block-form {
  background: #FCF5EA;
  border-radius: 4px;
  max-width: 560px;
  margin: 0 auto;
  padding: 32px clamp(20px, 4vw, 40px);
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.25);
}
.page-section:nth-of-type(9) .sqs-block-form input,
.page-section:nth-of-type(9) .sqs-block-form textarea {
  border: 1px solid var(--sc-line) !important;
  border-radius: 2px;
  background: #FFFFFF !important;
}

/* ---- Positioning Strip = section 6 ---- */
.page-section:nth-of-type(6) .fe-block {
  border-top: 1px solid var(--sc-line);
  padding-top: 16px;
  padding-bottom: 16px;
}

/* ---- Our Expertise = section 7: single centered card, not a
     2-column grid. Border-top differentiates it the same way as
     Services (ember) and Approach & Philosophy (gold) — here teal. ---- */
.page-section:nth-of-type(7) {
  border-top: 3px solid var(--sc-teal);
  border-bottom: 1px solid var(--sc-line);
}
.page-section:nth-of-type(7) .fe-block {
  max-width: 56ch;
  margin-left: auto;
  margin-right: auto;
}

/* ---- Insights = section 8: same differentiation technique,
     using sand as the fourth distinct accent color ---- */
.page-section:nth-of-type(8) {
  border-top: 3px solid var(--sc-sand);
  border-bottom: 1px solid var(--sc-line);
}

/* ---- Scroll-reveal target (used by code-injection-footer.html) ---- */
.sc-reveal {
  opacity: 0;
  transform: translateY(18px);
  transition: opacity .7s ease, transform .7s ease;
}
.sc-reveal.is-visible {
  opacity: 1;
  transform: none;
}
@media (prefers-reduced-motion: reduce) {
  .sc-reveal { opacity: 1; transform: none; transition: none; }
}

/* ---- Who We Serve — animated word-cycle heading ---- */
#sc-word-cycle {
  display: inline-block;
  font-style: italic;
  color: var(--sc-ember);
  transition: opacity .32s ease, transform .32s ease;
  min-width: 1ch;
}
#sc-word-cycle.sc-word-swapping {
  opacity: 0;
  transform: translateY(8px);
}
@media (prefers-reduced-motion: reduce) {
  #sc-word-cycle { transition: none; }
}

/* ============================================================
   Light / Dark toggle
   ============================================================ */

/* ---- Dark mode token overrides ---- */
:root[data-theme="dark"] {
  --sc-ink: #F3ECDD;
  --sc-ink-muted: #B7CBC3;
  --sc-line: #37473F;
  --sc-gold: #E3B94A;
  --sc-ember: #E89A7A;
  --sc-teal: #8FB0A6;
  --sc-sand: #C9AD87;
}
:root[data-theme="dark"] body {
  background: #1D2B27 !important;
  color: var(--sc-ink) !important;
}

/* ---- Toggle button ---- */
.sc-theme-toggle {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 34px; height: 34px;
  border: 1px solid var(--sc-line);
  border-radius: 50%;
  background: transparent;
  color: var(--sc-ink-muted);
  cursor: pointer;
  margin-left: 14px;
}

/* ============================================================
   Separate pages — shared dark hero header
   (For Families, For Family Offices, How We Work With You, Our Team)
   Fixed colors, not theme tokens, same reasoning as the homepage's
   dark bands above being hardcoded rather than tied to --sc-ink.
   ============================================================ */
.page-hero {
  position: relative;
  overflow: hidden;
  background: linear-gradient(160deg, #3D5850 0%, #2A3F38 100%);
  padding: clamp(56px, 9vh, 96px) 0 clamp(48px, 8vh, 72px);
}
.page-hero * { color: #FCF5EA !important; }
.page-hero h1, .page-hero h2 { color: #FCF5EA !important; }
.page-hero a { color: rgba(255, 255, 255, 0.75) !important; border-color: rgba(255, 255, 255, 0.3) !important; }

/* Small uppercase label above a card's heading — shared by the
   "For Families" page's blocks and the "How We Work With You"
   page's engagement cards */
.segment-label {
  display: block;
  font-size: 0.72rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--sc-ink-muted);
  margin-bottom: 10px;
}

/* ============================================================
   Page: For Families — stacked blocks
   Sized to their own content, not forced into equal-height
   cards like a grid would.
   ============================================================ */
.family-service-block {
  border-top: 3px solid var(--fsb-accent, var(--sc-gold));
  padding-top: 28px;
  margin-top: 44px;
}
.family-service-block:first-child { margin-top: 0; }
.family-service-block:nth-child(1) { --fsb-accent: var(--sc-gold); }
.family-service-block:nth-child(2) { --fsb-accent: var(--sc-ember); }
.family-service-block:nth-child(3) { --fsb-accent: var(--sc-teal); }
/* Scoped to this page only — .segment-label above is shared with
   the How-We-Work-With-You page's cards, whose small uppercase
   label style should stay untouched */
.family-service-block .segment-label {
  font-family: 'Playfair Display', Georgia, serif;
  font-weight: 600;
  font-size: 1.35rem;
  text-transform: none;
  letter-spacing: normal;
  color: var(--sc-ink);
  margin-bottom: 12px;
}
.family-service-block .practice-label {
  margin: 22px 0 10px;
  font-size: 0.76rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  font-weight: 600;
  color: var(--sc-ink-muted);
}

/* Dot-marker bullet list used on the For Families page (it uses
   Code Blocks, not native Squarespace bullets like Services did) */
.offer-list { list-style: none; margin: 0; padding: 0; display: flex; flex-direction: column; gap: 6px; max-width: 620px; }
.offer-list li { font-size: 0.9rem; line-height: 1.4; color: var(--sc-ink-muted); padding-left: 14px; position: relative; }
.offer-list li::before {
  content: '';
  position: absolute;
  left: 0; top: 7px;
  width: 4px; height: 4px;
  border-radius: 50%;
  background: var(--sc-ember);
}

/* ============================================================
   Page: How We Work With You — three-up engagement cards
   ============================================================ */
.engagement-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: clamp(24px, 4vw, 40px); }
.engagement-card { border-top: 3px solid var(--sc-gold); padding-top: 20px; }
.engagement-card:nth-child(2) { border-top-color: var(--sc-ember); }
.engagement-card:nth-child(3) { border-top-color: var(--sc-teal); }
.engagement-card h3 { font-size: 1.15rem; margin-bottom: 10px; }
.engagement-card p { margin: 0; font-size: 0.92rem; color: var(--sc-ink-muted); }
@media (max-width: 860px) {
  .engagement-grid { grid-template-columns: 1fr; gap: 32px; }
}

/* ============================================================
   Page: Our Team
   ============================================================ */

/* Stat row — only used on the Team page's hero */
.team-stats {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
  margin-top: 48px;
  text-align: center;
  border-top: 1px solid rgba(255, 255, 255, 0.16);
  padding-top: 36px;
}
.team-stat-num {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: clamp(2.2rem, 5vw, 3.2rem);
  color: var(--sc-gold) !important;
}
.team-stat-label { margin-top: 8px; font-size: 0.76rem; letter-spacing: 0.05em; }
@media (max-width: 620px) {
  .team-stats { grid-template-columns: 1fr; gap: 28px; }
}

/* Card grid — reflows automatically as you add more people */
.team-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(220px, 1fr)); gap: clamp(28px, 4vw, 40px); }
.team-photo {
  width: 100%;
  aspect-ratio: 4 / 5;
  object-fit: cover;
  border-radius: 2px;
  box-shadow: 0 10px 28px rgba(0, 0, 0, 0.15);
  margin-bottom: 16px;
}
.team-name { font-size: 1.1rem; font-weight: 600; }
.team-credentials { font-size: 0.8rem; font-weight: 400; color: var(--sc-ink-muted); margin-left: 6px; }
.team-role { margin-top: 4px; font-size: 0.86rem; color: var(--sc-teal); }

/* Open-role card — a dashed placeholder, distinct from the
   gradient/initials placeholder used for real hires whose
   photo just hasn't been added yet */
.team-photo--open {
  display: flex;
  align-items: center;
  justify-content: center;
  background: transparent;
  border: 1px dashed var(--sc-line);
  color: var(--sc-ink-muted);
  font-size: 0.78rem;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  text-align: center;
  line-height: 1.5;
}
.team-card--open .team-name { color: var(--sc-ink-muted); font-weight: 500; }

/* Placeholder avatar for anyone without a headshot yet —
   swap for a real Image Block once a photo is supplied */
.team-photo--placeholder {
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(160deg, var(--sc-ink), var(--sc-teal));
  color: #FCF5EA;
  font-family: 'Playfair Display', Georgia, serif;
  font-style: italic;
  font-size: 1.8rem;
}
```

> **Dark-band fix, worth understanding before you paste:** the rules targeting section 5 (The SC Capital Difference) and section 9 (closing RFP band) hardcode both background and text color rather than using the theme-linked ink token. A dark section that pulls its background from the same token used for text elsewhere on the page will break the moment dark mode flips that token to a light value — hardcoding both sides avoids it entirely.

---

## Step 5 · Code Injection

Go to **Settings > Advanced > Code Injection**, and paste the entire block below into the **Footer** field. This tags blocks in the sections listed in `revealSections` for scroll-reveal, cycles the animated word in Who We Serve, and adds the light/dark toggle button.

```html
<!--
  SC Capital — Settings > Advanced > Code Injection > Footer
  Paste this in full. See squarespace/custom-css.css for the
  matching styles (.sc-reveal, #sc-word-cycle, .sc-theme-toggle).

  Section numbers in `revealSections` below assume the homepage
  build order in content/homepage.md — adjust to match yours
  (see docs/SITEMAP.md).
-->
<script>
(function () {
  // Sections to fade in on scroll — adjust to match your real order.
  var revealSections = [1, 2, 3, 4, 5, 6, 7, 8, 9];
  var sections = document.querySelectorAll('.page-section');
  revealSections.forEach(function (n) {
    var section = sections[n - 1];
    if (!section) return;
    section.querySelectorAll('.fe-block').forEach(function (block) {
      block.classList.add('sc-reveal');
    });
  });

  var prefersReduced = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
  var targets = document.querySelectorAll('.sc-reveal');
  if (prefersReduced || !('IntersectionObserver' in window)) {
    targets.forEach(function (el) { el.classList.add('is-visible'); });
  } else {
    var io = new IntersectionObserver(function (entries) {
      entries.forEach(function (entry) {
        if (entry.isIntersecting) {
          entry.target.classList.add('is-visible');
          io.unobserve(entry.target);
        }
      });
    }, { threshold: 0.12, rootMargin: '0px 0px -6% 0px' });
    targets.forEach(function (el) { io.observe(el); });
  }

  // Who We Serve heading — cycles the emphasized word.
  // Wrap that one word in a Code block or a span with
  // id="sc-word-cycle" inside the heading to target it.
  var words = ['families', 'entrepreneurs', 'founders', 'creators', 'executives', 'family offices', 'partners', 'entertainers', 'athletes', 'women'];
  var wordEl = document.getElementById('sc-word-cycle');
  if (wordEl && !prefersReduced) {
    var i = 0;
    setInterval(function () {
      wordEl.classList.add('sc-word-swapping');
      setTimeout(function () {
        i = (i + 1) % words.length;
        wordEl.textContent = words[i];
        wordEl.classList.remove('sc-word-swapping');
      }, 320);
    }, 2200);
  }
})();
</script>

<script>
(function () {
  var root = document.documentElement;
  var stored = null;
  try { stored = localStorage.getItem('sc-theme'); } catch (e) {}
  if (stored === 'light' || stored === 'dark') root.setAttribute('data-theme', stored);

  var btn = document.createElement('button');
  btn.className = 'sc-theme-toggle';
  btn.type = 'button';
  btn.setAttribute('aria-label', 'Toggle dark mode');
  btn.textContent = '◐';
  btn.addEventListener('click', function () {
    var isDark = root.getAttribute('data-theme') === 'dark';
    var next = isDark ? 'light' : 'dark';
    root.setAttribute('data-theme', next);
    try { localStorage.setItem('sc-theme', next); } catch (e) {}
  });

  var navTarget = document.querySelector('#header .nav-wrapper, #header nav, #header');
  if (navTarget) navTarget.appendChild(btn);
})();
</script>
```

---

## Step 6 · Light / Dark Toggle — already included

No separate action needed — the toggle button, its styling, and the dark
mode token overrides are already part of the CSS and Code Injection pasted
in Steps 4–5. Three things worth knowing:

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

---

## Step 7 · Section Position Number Map

Both the CSS and the Code Injection script target sections by position,
counting from the top starting at 1. If you built Step 3 in the listed
order, this is already correct:

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

If a number doesn't match your actual build, the effect will show up on
the wrong section — correct the number everywhere it appears (in both the
CSS and the Code Injection script), save, and refresh. None of the four
separate pages from Step 3b are in this list.

---

## Step 8 · Preview & Publish Checklist

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
      not light-on-light or light-on-dark); confirm the single-card Our
      Expertise section reads correctly
- [ ] Review the footer disclaimer and contact details for accuracy
- [ ] **Do not migrate anything to the live site.** This build stays on
      the duplicate (`helicon-grey-ab5r`) until a human reviews it and
      decides to move it over themselves.

---

## Appendix · Footer copy

## Footer

**Firm**
SC Capital, LLC
Saint Petersburg, Florida

**Contact**
Stephen Collins, Founder & CEO
(843) 303-3331
stephen@sccapitalllc.com

**Site** — About · Who We Serve · Services · Insights · Family Login

**Legal** — Disclaimer · Privacy Policy · Terms of Use · LinkedIn (new tab:
`https://www.linkedin.com/company/sc-capital-llc-sc-capital-holdings-llc-scc/`)

**Legal disclaimer line:** This website is for informational purposes only

---

## Appendix · Legal Pages (Disclaimer, Privacy Policy, Terms of Use)

These three pages already exist live at `/disclaimer`, `/privacy-policy`, and `/terms-of-use` — on the **live** site, not this duplicate. **Do not attempt to edit or publish the live legal pages from this session.** The text below is provided for reference only, in case the duplicate site needs placeholder legal pages built for preview purposes; the entity-name edit it contains ("SC Capital Holdings, LLC (SCC)" removed throughout) needs sign-off from the firm's legal/compliance counsel before it's ever published anywhere live — flag this to the person you're working with rather than publishing it yourself.

**Slugs:** `/disclaimer`, `/privacy-policy`, `/terms-of-use` — already live.
Simple text pages (native Squarespace text blocks), no special CSS or
layout. Linked from the footer's "Legal" column.

**Important:** this text already reflects one deliberate edit from what's
currently published live — every mention of **"SC Capital Holdings, LLC
(SCC)"** has been removed; the mockup reads just **"SC Capital, LLC"**
everywhere that compound name appeared, including in this legal text. Since
this changes language your compliance/legal counsel may have already
reviewed and filed, **confirm the entity-name change with them before
publishing** the updated pages.

---

## Disclaimer

All persons using the SC Capital, LLC website ("Site") expressly agree to
the foregoing disclaimer as a pre-condition to using this Site for any
purpose whatsoever. The materials on the Site including, without
limitation, news articles, informational materials and all other
manager-specific information, have been prepared for informational
purposes only and do not constitute financial, legal, tax or any other
advice. All information contained herein is provided "as is" and
SC Capital, LLC expressly disclaims making any express or implied
warranties with respect to the fitness of the information contained
herein for any particular usage, its merchantability or its application or
purpose. Prior to making any investment or hiring any investment manager
you should consult with a professional financial advisor, legal and tax
advisor to assist in due diligence as may be appropriate and determining
the appropriateness of the risk associated with a particular investment.
In no event shall SC Capital, LLC be responsible or liable for the
correctness of any such material or for any damage or lost opportunities
resulting from use of this data.

Users of the SC Capital, LLC website may view, download and print
information and materials on this Site for its personal and internal
business use provided that all hard copies contain all copyright and
other applicable notices. All users may not reproduce, modify, copy,
alter in any way, distribute, sell, resell, transmit, transfer, license,
assign or publish any information obtained from this Site. Registered
User shall not use this site at any time for any purpose that is unlawful
or prohibited and shall comply with any applicable local, state, national
or international laws or regulations when using this Site.

SC Capital, LLC, and the logos and marks included on the SC Capital, LLC
site that identify SC Capital, LLC services and products are proprietary
materials. The use of such terms and logos and marks without the express
written consent of SC Capital, LLC is strictly prohibited. Copyright in
the pages and in the screens of the Site, and in the information and
material therein, is proprietary material owned by SC Capital, LLC unless
otherwise indicated. The unauthorized use of any material on the
SC Capital, LLC website may violate numerous statutes, regulations and
laws, including, but not limited to, copyright, trademark, trade secret
or patent laws.

---

## Privacy Policy

### Privacy Statement

SC Capital, LLC is committed to respecting and protecting your Privacy. We
have structured our Web site so that, in general, you can visit
SC Capital, LLC on the Web without identifying yourself or revealing any
personal information. Once you choose to provide us personally
identifiable information (any Information by which you can be
identified), you can be assured that it will only be used to support your
contact/client relationship with SC Capital, LLC.

### Awareness

SC Capital, LLC provides this Online Privacy Statement to make you aware
of our privacy policy, practices and of the choices you can make about
the way your information is collected and used.

### What we collect

SC Capital, LLC in some instances you can subscribe to different events
and seminars, make requests, and register to receive various marketing
materials. The types of personal information collected at these pages are
name, contact and some preference information. In order to tailor our
subsequent communications to you and continuously improve our products
and services (including registration), we may also ask you to provide us
with information regarding your professional interests, demographics and
more detailed contact preferences.

### How we use it

SC Capital, LLC uses your information to better understand your needs and
provide you with better service, whether as a visitor of the firm,
contact or client. From time to time, we may also use your information to
contact you for market research or to provide you with marketing
information we think would be of particular interest. At a minimum, we
will always give you the opportunity to opt out of receiving such direct
marketing or market research contact. We will also follow local
requirements, such as allowing you to opt in before receiving unsolicited
contact, where applicable.

### Who we share it with

SC Capital, LLC will not sell, rent, or lease your personally identifiable
information to others. Unless we have your permission or are required by
law, we will only share the personal data you provide online with other
SC Capital, LLC entities and/or business partners who are acting on our
behalf for the uses described in "how we use it". Such SC Capital, LLC
entities and/or business partners are governed by our privacy policies
with respect to the use of this data and are bound by the appropriate
confidentiality agreements.

### Choice

SC Capital, LLC will not use or share the personally identifiable
information provided to us online in ways unrelated to the ones described
above without first letting you know and offering you a choice. As
previously stated, we will also provide you the opportunity to let us
know if you do not wish to receive unsolicited direct marketing materials
from us and we will do everything we can to honor such requests. Your
permission is always secured first, should we ever share your information
with third parties that are not acting on our behalf and governed by our
privacy policy.

### Accuracy & Access

SC Capital, LLC strives to keep your personally identifiable information
accurate. We will provide you with access to your information, including
making every effort to provide you with online access to your
registration data so that you may view, update or correct your
information. To protect your privacy and security, we will also take
reasonable steps to verify your identity before granting you access or
enabling you to make corrections. To access your personally identifiable
information, return to the webpage where you originally entered it and
follow the instructions on that web page. This opt-out will cancel all
marketing and support communication and newsletters, including offline
subscriptions. Certain areas of SC Capital, LLC's website may limit
access to specific individuals through the use of passwords and through
providing personal data. Links to Third party web sites on the site are
provided solely as a convenience to you. If you use these links, you will
leave the SC Capital, LLC site. SC Capital, LLC has not reviewed all of
these third party sites and does not control and is not responsible for
any of these sites, their content or their privacy policy. Thus,
SC Capital, LLC does not endorse or make any representations about them,
or any information, software or other products or materials found there,
or any results that may be obtained from using them. If you decide to
access any of the third party sites linked to this site, you do so at
your own risk.

### Security

SC Capital, LLC is committed to ensuring the security of your
information. To prevent unauthorized access or disclosure, maintain data
accuracy, and ensure the appropriate use of information, we have put in
place appropriate physical, electronic, and managerial procedures to
safeguard and secure the information we collect online. We use encryption
when collecting or transferring sensitive data.

---

## Terms of Use

The following terms and conditions govern the use of this website, which
is managed and operated by SC Capital, LLC. By using this website and the
online services operated or offered by SC Capital, LLC (collectively the
"Site"), you agree to these Terms and Conditions.

### Privacy

When you use or interact with us via our website, or interact with us via
electronic communications, we (or our service providers on our behalf)
may automatically collect technical and navigational and location
information, such as device type, browser type, Internet protocol
address, pages visited, and average time spent on our site. We use this
information for a variety of purposes, such as facilitating site
navigation, improving the design and functionality of our website and
electronic communications, and personalizing your experience.
Additionally, the following policies and practices apply when you are
online.

### Cookies and similar technologies

SC Capital, LLC and our third-party service providers may use cookies and
similar technologies ("cookies") to support the operation of and maintain
our website. Cookies are small amounts of data that a website or online
service exchanges with a web browser or application on a visitor's device
(for example, computer, tablet, or mobile phone). Cookies help us to
collect information about users of our digital offerings, including date
and time of visits, pages viewed, amount of time spent using our digital
offerings, or general information about the device used to access our
website.

Both SC Capital, LLC and third-party service providers we hire, such as
Google, may use cookies and other technologies, such as web beacons, tags,
or mobile device ID, in online advertising as described below. Most
browsers and mobile devices offer their own settings to manage cookies. If
you use those settings to refuse or delete cookies it may negatively
impact your experience using our website, as some features on our website
may not work properly. Depending on your device and operating system, you
may not be able to delete or block all cookies.

We may collect analytics data or use third-party analytics tools such as
Google Analytics to help us measure traffic and usage trends for our
digital offerings and to understand more about the demographics of our
users. You can learn more about Google's practices with Google Analytics
by visiting Google's privacy policy. You can also view Google's currently
available opt-out options.

For information about your privacy, please see our Privacy Policy.

### Links

Clicking on certain links within the Site or certain other websites that
are linked to the Site may take you to other websites, or may display
information on your computer screen from other websites, which may not be
maintained by SC Capital, LLC. Such websites may contain terms and
conditions, privacy provisions, confidentiality provisions, or other
provisions that differ from the terms and conditions applicable to the
Site. Links to other Internet services and websites are provided solely
for the convenience of users. A link to any service or website is not an
endorsement of any kind of the service or website, its content, or its
sponsoring organization.

SC Capital, LLC assumes no responsibility or liability whatsoever for the
content, accuracy, reliability or opinions expressed in a website, to
which the website is linked (a "linked website") and such linked websites
are not monitored, investigated, or checked for accuracy or completeness
by SC Capital, LLC. It is your responsibility to evaluate the accuracy,
reliability, timeliness and completeness of any information available on
a linked website. All products, services and content obtained from a
linked website are provided "as is" without warranty of any kind, express
or implied, including, but not limited to, implied warranties of
merchantability, fitness for a particular purpose, title,
non-infringement, security, or accuracy.

### Limited Liability

Neither SC Capital, LLC nor any other party involved in the creation,
production or delivery of the information at the website, nor the
officers, directors, employees or representatives of SC Capital, LLC, are
liable in any way for any indirect, special, punitive, consequential, or
indirect damages (including without limitation lost profits, cost of
procuring substitute service or lost opportunity) arising out of or in
connection with the website or the use of the website or a linked website
or with the delay or inability to use the website or a linked website,
whether or not SC Capital, LLC is made aware of the possibility of such
damages. This limitation includes, but is not limited to, the
transmission of any viruses, data or harmful code that may affect your
equipment or anyone else's equipment, any incompatibility between the
website's files and your browser or other website accessing program, or
any failure of any electronic or telephone equipment, communication or
connection lines, unauthorized access, theft, operator errors, or any
force majeure. SC Capital, LLC does not guarantee continuous,
uninterrupted or secure access to the website or a linked website. The
content, accuracy, opinions expressed, and other links provided by linked
websites are not necessarily investigated, verified, monitored or
endorsed by SC Capital, LLC. The information, software, products and
description of services published on the website or a linked website may
include inaccuracies or typographical errors, and SC Capital, LLC
specifically disclaims any liability for such inaccuracies or errors.
Changes are periodically made to the information on the website and
linked websites. SC Capital, LLC may make improvements or changes to the
website at any time.

### No Warranties

All products, services and content on the website are provided "as is"
without warranty of any kind, express or implied, including, but not
limited to, implied warranties of merchantability, fitness for a
particular purpose, title, non-infringement, security, or accuracy.
SC Capital, LLC does not endorse and is not responsible for the accuracy
or reliability of any information on the website. It is your
responsibility to evaluate the accuracy, reliability, timeliness and
completeness of any information available on the website. SC Capital, LLC
specifically disclaims any duty to update the information on the website.
You agree to indemnify, defend, and hold SC Capital, LLC harmless from any
liability, losses, damages, penalties, claims and expenses, including
attorney's fees related to your violation of these terms of use or the
use of the services and information provided at the website.

### Confidentiality of Information

SC Capital, LLC has taken reasonable steps to ensure the confidentiality
of information taken at the Website and transmitted via the Internet.
However, unexpected changes in technology may be used by unauthorized
third parties to intercept confidential information and we cannot be
responsible should confidential information be intercepted and
subsequently used by an unintended recipient.

Please read our Privacy Policy for further information on confidentiality
of information.

### Website Content and Material

The information and materials contained in the Site, including but not
limited to these Terms and Conditions and any product information, are
subject to change without notice. You are deemed to be apprised of and
bound by any such changes. Not all products and services are available in
all geographic areas. Your eligibility for particular products and
services is subject to final determination and acceptance by us.

### Waiver and Severability

Any waiver of any provision contained in these Terms and Conditions shall
not be deemed to be a waiver of any other right, term or provision of
these Terms and Conditions. If any provision in these Terms and Conditions
shall be or become wholly or partially invalid, illegal or unenforceable,
such provision shall be enforced to the extent it is legal and valid and
the validity, legality and enforceability of the remaining provisions
shall in no way be affected or impaired thereby.

### Access and Interference

You agree not to engage in any of the following:

- Use any robot, spider, scraper, deep link or other similar automated
  data gathering or extraction tools, program, algorithm or methodology
  to access, acquire, copy or monitor the Site or any portion of the
  Site, without SC Capital, LLC's express written consent, which may be
  withheld in SC Capital, LLC's sole discretion.
- Use or attempt to use any engine, software, tool, agent, or other
  device or mechanism (including without limitation browsers, spiders,
  robots, avatars or intelligent agents) to navigate or search the Site,
  other than the search engines and search agents available through the
  Site and other than generally available third-party web browsers.
- Post or transmit any file which contains viruses, worms, Trojan horses
  or any other contaminating or destructive features, or that otherwise
  interfere with the proper working of the Site.
- Attempt to decipher, decompile, disassemble, or reverse-engineer any of
  the software comprising or in any way making up a part of the Site.

### Secured Areas

Access to and use of password protected and/or secure areas of the
Website is restricted to authorized users only. Unauthorized persons
attempting to access these areas of the website may be subject to
prosecution.

### Electronic Communications

The Site provides you SC Capital, LLC e-mail addresses so that you may
communicate electronically by sending an e-mail message SC Capital, LLC.
All e-mail sent to and from SC Capital, LLC will be received or otherwise
recorded by the SC Capital, LLC e-mail system and is subject to archival,
monitoring or review by and/or disclosure to, someone other than the
recipient. Communications through the website may involve the electronic
transmission, to any e-mail address you provided to us, of information
that you may consider to be personal financial information and you agree
and consent to such transmission of such information. You agree not to
use e-mail to transmit any confidential personal information. It is your
responsibility to update or change your e-mail address, as appropriate.
