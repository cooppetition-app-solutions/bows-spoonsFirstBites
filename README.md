# Bows and Spoons — First Bites (marketing website)

The client-facing website for **Bows and Spoons First Bites**, a gentle,
science-backed allergen introduction kit for infants. *First Bites. Big Steps.™*

It's a static, zero-build, mobile-first site with **light (cream) and dark (navy)
themes**, built on the brand identity — the bow-spoon-heart mark, an elegant
serif (Fraunces) paired with Inter, a soft lavender accent — and the **First Bites
design system** it inherits from ([bows-spoonsFirstBites](https://github.com/JeffTrakk/bows-spoonsFirstBites),
`design-system/`), including the health-status semantic colours.

> **Not a medical device.** This product and site do not diagnose allergy and are
> not a substitute for professional medical advice. Always consult your
> pediatrician before introducing allergens. In an emergency, call 911.

## What's here

| Path | What it is |
| --- | --- |
| `index.html` | The whole website — self-contained (inline CSS + inline SVG), so it deploys and previews with zero dependencies. |
| `brand-tokens.css` | The brand token set as a standalone reference (same tokens inlined in `index.html`), for building more pages. |
| `assets/mark.svg` | The bow-spoon-heart logo mark as a reusable, themeable SVG. |
| `vercel.json` | Static-deploy config (clean URLs, cache headers). |

## Sections

Hero · Why it works (the four pillars: Safe & Science-backed · Parent Approved ·
Gentle Introductions · Access for All) · How it works (the 8-allergen, 24-day
ladder) · Safety · The companion app · Testimonials · Order · FAQ · Footer.

## Run it

No build step. Serve the folder:

```
python3 -m http.server 8000
# then open http://localhost:8000/
```

## Deploy to Vercel

The site is fully static — no framework, no build command.

- **Dashboard** — import this repo at [vercel.com/new](https://vercel.com/new);
  Framework Preset **Other**, no build command, output directory `.` (root). Deploy.
- **CLI** — `npm i -g vercel`, then `vercel` from the repo root.

## Brand

- **Logo** — the bow-spoon-heart mark (`assets/mark.svg`); the bow inherits
  `--brand-lavender`, the spoon takes the ink colour via `currentColor`.
- **Wordmark** — "bows *and* spoons" in Fraunces, with *and* in soft lavender.
- **Tagline** — First Bites. Big Steps.™
- **Colour** — cream `#f6f1e8` + navy `#1b1c2e`, lavender `#a99cdb`; health-status
  greens/ambers/corals from the design system.
- **Type** — Fraunces (display) over Inter (body/UI).

## Design tokens

Everything reads from CSS custom properties (see `brand-tokens.css`). Themes are
token-level: bare `:root` is the complete light palette; `@media (prefers-color-scheme:dark)`
and `:root[data-theme="dark"]` redefine only the tokens, so light and dark stay in
step and the on-page toggle wins in both directions.

---

Built on the [First Bites design system](https://github.com/JeffTrakk/bows-spoonsFirstBites).
