# Page: Our Team

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
