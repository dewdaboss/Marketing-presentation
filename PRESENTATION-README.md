# Digital Marketing & Growth Strategy
### Creative Team Production — Indore
A premium, cinematic 16:9 client presentation. Single self-contained page, no build step, no network dependency.

---

## Open it

```bash
# from this folder
python3 -m http.server 8080
# then open http://localhost:8080
```

Or simply double-click `index.html` — it works offline straight from the filesystem.

---

## Controls

| Action | Keys / input |
|---|---|
| Next slide | `→` `Space` `Enter` `↓` `PageDown` · click right side · swipe left · scroll down |
| Previous slide | `←` `↑` `PageUp` · click left side · swipe right · scroll up |
| Jump to any slide | click anywhere on the progress bar at the bottom |
| Fullscreen | `F` |
| **Export to PDF** | `P` |

### Exporting a PDF
Press **P**. Every slide's animation is completed instantly so all 24 frames are fully rendered, then the print dialog opens.
Choose **Save as PDF**, **landscape**, **no margins**, and enable **background graphics**.
Result: a 24-page, 16:9 PDF with one slide per page.

---

## Adding the official logo

The presentation looks for the official Creative Team Production logo at:

```
assets/logo.svg      ← preferred
assets/logo.png      ← fallback
```

Drop your official file in as `logo.svg` (or `logo.png`) and it appears automatically in the header of every slide and on the closing frame.

Until then, the presentation shows a clean **typographic wordmark** ("CREATIVE TEAM PRODUCTION / INDORE"). No logo symbol is drawn, traced, or invented, and no third-party logos are used anywhere in the deck.

---

## The 24 slides

| # | Slide | # | Slide |
|---|---|---|---|
| 01 | Cover — *Don't just create content. Build a brand.* | 13 | Meta Ads funnel — attention → action |
| 02 | The real problem — posting content is not marketing | 14 | Ad creative testing — A/B/C/D variants |
| 03 | Our approach — the marketing system | 15 | Targeting — audience, message, moment |
| 04 | Understand the brand first | 16 | Retargeting — the return journey |
| 05 | Audience research — the audience map | 17 | Organic + paid → one growth system |
| 06 | Competitor & market research | 18 | Monthly workflow — 8 phases |
| 07 | Content strategy — six content pillars | 19 | Data & analytics — the dashboard |
| 08 | Content we can create | 20 | Reporting — transparent marketing |
| 09 | Reels strategy — hook → CTA | 21 | What makes us different |
| 10 | Organic growth — the long-term game | 22 | The growth mindset loop |
| 11 | Our organic growth loop | 23 | The whole process in one frame |
| 12 | Meta Ads — audience + creative + offer | 24 | Final — *Let's build something people remember.* |

---

## Design system

**Palette** — strictly the brand's three colours:

| Role | Value | Share |
|---|---|---|
| Black (ground) | `#070808` | ~80% |
| Neon green (accent) | `#A8FF35` | ~15% |
| White (type) | `#FFFFFF` | ~5% |

**Typography** — self-hosted, so rendering is identical online and offline:
- **Inter** 300–800 — headlines and body (`vendor/fonts/`)
- **Space Grotesk** 400–700 — labels, eyebrows, numerals (`vendor/fonts/`)

**Motion** — GSAP 3.12.5 (`vendor/gsap.min.js`): masked word-by-word reveals, staggered card builds,
animated funnel stages, ecosystem rings, split-screen merge, timeline scrub, animated bar chart with
count-up KPIs, and a cinematic close on the final frame.

---

## Content policy — what the deck deliberately does *not* contain

Verified by an automated pass over the rendered text:

- ❌ No pricing, packages, monthly fees, retainers, or discounts — **zero occurrences**
- ❌ No fake testimonials, and no fake client results
- ❌ No guaranteed followers, leads, sales, or reach
- ❌ No third-party logos (the Meta logo is not used; ads are shown as a generic social interface)
- ❌ No invented logo mark — only the official logo file, or a neutral wordmark

Analytics on slides 19 and 20 are explicitly labelled **"illustrative example"**, **"Demo data"**,
and **"not client results"**, so a viewer can never mistake them for real campaign performance.

Slide 10 states results are *"earned through consistency and quality, not promised overnight."*

---

## Files

```
index.html                 the entire presentation (markup + styles + engine)
vendor/gsap.min.js         animation library (local copy)
vendor/fonts/*.woff2       Inter + Space Grotesk (local copies)
assets/                    put the official logo here as logo.svg / logo.png
PRESENTATION-README.md     this file
```

### Editing tips
- All slide content lives in clearly separated `<section class="slide" id="sN">` blocks in `index.html`.
- Each slide's animation is one `switch` case in `animSlide()`; its start state is the matching case in `resetSlide()`.
- The palette lives in CSS custom properties at the top of the file (`--black`, `--green`, `--white`).
