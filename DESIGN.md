# Design

## Theme

Dark. The physical scene: *a UK retail trader, 32, on a 27-inch monitor at 09:15 GMT before the New York open, second coffee, weighing whether to book a call with this site or close the tab.* That scene forces a confident, premium, dark-mode aesthetic that feels institutional rather than recreational. Light mode is not a default to chase.

The atmosphere reference is *Bloomberg Terminal at low brightness*, not *crypto-bro neon*. The dark must feel quiet and luxurious, not flashy.

## Color

**Strategy: Committed.** One saturated brand colour (antique gold) carries the identity, with a black-to-amber diagonal gradient as the load-bearing canvas. Tinted near-black neutrals (warm undertone, chroma ~0.01 toward the gold hue) for surfaces. One reserved emerald for `positive` status and a muted red for `negative` — both used sparingly on data only.

The gold reference is *Bloomberg Terminal amber* — institutional, archival, slightly desaturated — explicitly NOT *Rolex marketing* or *VIP casino chip*.

| Role | Hex | Notes |
|---|---|---|
| Canvas top-left | `#000000` | absolute black, anchor of the diagonal |
| Canvas mid | `#100C05` | warm near-black with amber undertone |
| Canvas mid-amber | `#1F1808` | transition midpoint |
| Canvas bottom-right | `#3A2B0E` | deep amber, gradient terminus |
| Brand gold (main) | `#C9A45E` | accents, equity-curve stroke, labels, recommend tag |
| Brand gold (mid) | `#B89244` | primary CTA gradient mid stop |
| Brand gold (deep) | `#8E7227` | primary CTA gradient deep stop, hover |
| Ink primary | `#F5F5F7` | body text on dark |
| Ink soft | `rgba(245,245,247,0.78)` | secondary copy |
| Ink muted | `rgba(245,245,247,0.56)` | tertiary copy, captions |
| Ink faint | `rgba(245,245,247,0.36)` | disabled, axis labels |
| Positive | `#34D399` | profit %, status dot |
| Negative | `#F87171` | loss %, used minimally |
| Border | `rgba(255,255,255,0.08)` | hairline dividers |
| Border strong | `rgba(255,255,255,0.16)` | hover/active borders |
| Border gold | `rgba(201,164,94,0.32)` | recommended pricing card border |

No `#000` or `#fff` for elevated surfaces — every neutral is tinted toward the warm amber hue. Pure black is reserved for the canvas anchor only.

Risk flag (for future Impeccable audits): black + gold sits on the first-order finance reflex (*"finance → navy and gold"*). Mitigations: muted gold value (#C9A45E, not bright safety-cone yellow), warm-black canvas tint (not pure cool grey), gold reserved for accents not surfaces.

## Typography

**Display:** Fraunces (variable, optical-size + weight). Currently used for h1, h2, h3, plan-name, footer "Algo" wordmark.

> **Note:** Fraunces is on the Impeccable reflex-reject list. It was committed to as part of the existing identity, so identity-preservation applies — but greenfield-mode work should consider replacements. The audit will flag whether the current choice serves the brand or should be swapped (likely candidate: a more institutional sans like ABC Diatype, GT America, or a single committed sans family with strong weight contrast).

**Body:** Geist (variable). Modern, clean sans, distinctive enough for a fintech voice without reading as generic system-ui.

**Data / Mono:** Geist Mono. Tabular numerals enforced via `font-variant-numeric: tabular-nums`. Used for every figure: percentages, prices, dates, timestamps, axis labels.

**Display accent:** Avalanche (Pangram Pangram, paid). Wired via `@font-face` to `media/fonts/Avalanche.woff2`. Currently applied to the `.stroke` line ("Trade hands-free.") in the hero. Falls back to Bricolage Grotesque if missing.

**Scale:** Fluid `clamp()` on h1/h2/h3 with ratio ≥1.25 between steps. Light text on dark gets +0.05 line-height to compensate for perceived weight loss.

## Spacing & Layout

Fluid `clamp()` for section padding (`5–9.5rem`) and content blocks. Container max-width `1240px`, padding-inline `clamp(1.25rem, 4vw, 2.5rem)`. Hero overrides the container to use a wider 1440-equivalent edge so the hero text anchors flush-left near the viewport edge.

Layout is currently centred-stack-leaning. The audit will likely call for asymmetric break-the-grid moves on Results and Trust to escape the SaaS-template default.

## Surfaces & Components

**Glassmorphism is the dominant surface treatment** — every card (steps, results, pricing, trust, trades, hero) uses translucent white-on-dark with `backdrop-filter: blur(20–32px) saturate(180–200%)`. This is on the Impeccable absolute-bans list when used decoratively. Polish must reduce glass to one or two purposeful moments and rebuild other surfaces with hairline-bordered or plain-edge editorial cells.

Hairline borders (`rgba(255,255,255,0.08)`) and elevated shadow (`0 1px 0 inset highlight + 0 14px 56px depth`) define glass cards.

Border-radius: `--radius: 18px`, `--radius-lg: 28px` (final CTA), `--radius-sm: 12px`.

## Motion

Existing motion budget:

- Hero typing animation on system message (one-shot, 38ms/char)
- Status dot pulse (1.8s ease-out infinite, one element only)
- Hero h1 per-line stagger reveal (280/460/640ms delay, ease-out cubic)
- Hero card / lede / CTA row staggered fade-up
- Number count-up via `IntersectionObserver` + `requestAnimationFrame`, 1500ms easeOutCubic
- Equity curve stroke-dasharray draw (2s ease-out, scroll-triggered)
- Section fade-up (700ms ease-out cubic on every `.fade-up`)
- Tickertape marquee (90s linear infinite)
- Final CTA equity-curve stroke draw (2.5s)
- All gated behind `prefers-reduced-motion: reduce`

Every easing curve is exponential ease-out (`cubic-bezier(0.2, 0.7, 0.2, 1)` or default ease-out). No bounce or elastic.

The fade-up on every section is over-applied — should be reduced to 2–3 deliberate motion moments only.

## Imagery

The hero plays a 16-second 1080p MP4 (`media/hero.mp4`, ~15MB) with `autoplay muted loop playsinline`. The video is masked at the bottom with a vertical fade so it eases into the page gradient.

There is currently **no founder photograph** anywhere on the site. The Trust section references "Built by a trader. For traders." but doesn't show one. This is a known gap.

There is no Glasgow map, no TradingView screenshot, no broker integration screenshot. The site's "show don't tell" principle (PRODUCT.md) is currently violated.

## Fonts in Use

```css
@font-face { font-family: 'Avalanche'; src: url('media/fonts/Avalanche.woff2') format('woff2'); font-weight: 100 900; font-display: swap; }

/* via Google Fonts */
font-family: 'Fraunces', serif;             /* display */
font-family: 'Bricolage Grotesque', sans;    /* fallback for stroke line */
font-family: 'Geist', sans-serif;            /* body */
font-family: 'Geist Mono', monospace;        /* data */
```

## Anti-pattern flags (project-specific, for audit)

- Glassmorphism on every surface (default rather than purposeful)
- Gradient-text section labels (`background-clip: text` on `.label`) — Impeccable absolute ban
- Hero-metric layout (big number + small label) on the hero stats strip and results card
- Identical-card grid for "How It Works" (3 same-sized cards with number + heading + text)
- No imagery / face on a brief that arguably implies one (founder portrait for trust)
- Fraunces in display position despite being on the reflex-reject list
- Editorial-typographic accumulation (small mono labels with rules + display serif) drifting into the saturated AI lane
