# Homepage Content

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
