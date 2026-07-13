# CLAUDE.md — Cyber7 Group Holding Company Website

## Project Overview

Website for **Cyber7 Group LLC** — presented as the "Cyber 7 Family of Companies" (owner's preferred phrasing over "holding company"). This site's job is simple: explain what the group is and route visitors to the three business-unit sites. It intentionally stays lean (one page).

| Business Unit | Focus | Domain | Accent color |
|---|---|---|---|
| C7 MSP | Managed IT / cybersecurity | c7msp.com | amber #f2a93b |
| C7 Infrastructure | Data center / systems integration | c7infrastructure.io | blue #2f6fd0 |
| C7 Intelligence | AI integration / custom software | c7intelligence.io | violet #8b5cf6 |

**Design concept:** the parent site is deliberately **neutral** (white/graphite with the shield's red #c0453a as accent) while each unit card carries its child brand's accent color — the umbrella visually "contains" the three brands. Do not let the parent site adopt any single child's palette.

**Note:** this replaces the previous cyber7group.com (old MSP-focused site, formerly on Squarespace). MSP-specific content now lives at c7msp.com.

## Tech Stack & Hosting

- Pure static HTML/CSS — single `index.html`, no build step, no JS.
- Hosted on GitHub Pages — deploy from `main` branch, root folder.
- Custom domain: cyber7group.com (GoDaddy DNS → GitHub Pages A records + www CNAME). NOTE: DNS is currently pointed at the old site host (likely Squarespace); switching the A/CNAME records to GitHub Pages is the cutover step. Email on this domain (e.g. domains@cyber7group.com, info@cyber7group.com) uses MX records — do NOT touch MX records during the DNS cutover.
- Public repo — no secrets, keys, client names, or internal info, ever.

## Repo Structure

```
index.html                      # entire site (markup + CSS in one file)
CLAUDE.md                       # this file
assets/
  c7-shield.png                 # shield mark (nav, hero watermark)
  c7group-logo-light.png        # full logo, light wordmark (dark footer)
  c7group-logo-dark.png         # full logo, original dark wordmark (spare, for light bg)
  favicon.png                   # 64px shield favicon
```

## Design System

- **Fonts:** Archivo (headings/UI), Inter (body)
- **Palette (CSS variables in `:root`):** `--white` #ffffff, `--smoke` #f5f5f4, `--graphite` #1c1b1a / `--graphite-2` #262524, `--red` #c0453a (from shield logo), plus per-unit accents `--msp` / `--infra` / `--intel` used ONLY on the unit cards.
- **Feel:** clean corporate holding-company page. Big Archivo headline, faint oversized shield watermark in the hero, unit cards with colored top bars and arrow hover states, dark graphite about band and footer.

## Page Sections (in order)

1. Header/nav — shield + CYBER7GROUP wordmark (red 7), anchor links
2. Hero — "One group. Three ways we move technology forward." + faint shield watermark
3. Our Companies (`#companies`) — 3 unit cards linking out to the three sites (color-coded, open in new tab)
4. About (`#about`) — dark band; the "why a holding company" story + the shared Cyber7 standard (senior engineering, vendor-agnostic, documentation, built for day two)
5. Contact (`#contact`) — "Not sure which company you need?" router framing; phone + email box
6. Footer — light-wordmark logo, unit links, copyright

## Key Content Facts

- **Phone:** 502-473-5020
- **Email:** info@cyber7group.com ← verify this mailbox exists (domains@cyber7group.com is known to exist on this domain)
- No LinkedIn links per owner preference (consistent with sibling sites)
- "Three decades of hands-on engineering" refers to the principal's ~30 years of experience

## Known Issues / TODO

- Verify info@cyber7group.com mailbox before launch.
- DNS cutover from old site host to GitHub Pages is pending — see hosting note above (preserve MX records).
- Old cyber7group.com content (stats, services, flat-fee copy) was migrated to c7msp.com — nothing further needed from the old site unless the owner wants an archive.

## Conventions for Edits

- Keep everything in the single `index.html`.
- Parent stays neutral: graphite/white/red only, except unit-card accents.
- Unit descriptions must stay short (2–3 lines) — this page routes, it doesn't sell; each child site does its own selling.
- Footer keeps the three unit links.
