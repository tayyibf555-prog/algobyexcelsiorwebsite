# Algo by Excelsior

Single-page landing site for **Algo by Excelsior** — a UK-based automated mechanical trading system that executes Nasdaq and Gold trades via TradingView.

## Quick start

```bash
# Serve locally (anywhere with python3)
python3 -m http.server 8000
# then open http://localhost:8000/
```

No build step. The site is one self-contained `index.html` with embedded CSS and JS.

## File layout

```
index.html              the entire site
PRODUCT.md              strategic brief (audience, brand voice, anti-references)
DESIGN.md               visual system (palette, type, motion, components)
logo/algo-logo.png      transparent gold logo, used in nav + footer
media/hero.mp4          hero video asset (currently unused; reserved)
media/fonts/            local @font-face files (Avalanche fallback)
.claude/                local Impeccable skill files (dev-time only)
```

## Going live — checklist

Set these constants at the top of the `<script>` block in `index.html`:

| Constant | What it does |
|---|---|
| `CALENDLY_URL` | The free 15-min discovery-call booking link. Also used by the Lifetime "Enquire" button (POA tier). |
| `WHATSAPP_NUMBER` | E.164 format with no spaces, e.g. `+447xxxxxxxxx`. Leave empty to hide the WhatsApp line entirely. |
| `WHATSAPP_DISPLAY` | How the number is rendered on screen. |
| `CHECKOUT_SUBSCRIPTION_URL` | Stripe Checkout (or other provider) URL for the £1,000/month tier. Configure the session's `success_url` to redirect to your Calendly onboarding link so the buyer lands on booking immediately after payment. |

Every CTA disables itself (cursor: not-allowed, "not yet configured" tooltip) until the relevant URL is set, so the site is safe to deploy with placeholders without leading users to dead links.

## Compliance reminders (FCA-friendly)

- No "guaranteed", "risk-free", or "passive income" copy anywhere.
- Footer disclaimer remains verbatim.
- All CTAs say "Book a Call" / "Discovery Call" / "Get Started" / "Enquire" — never "Buy" alone.
- British English throughout.
- FCA status surfaced in `.trust-meta` and `.footer-disclaimer` (not authorised or regulated).

## Theme

Black + antique gold (`#C9A45E`). Tinted-warm near-black canvas with a subtle 135° gradient toward `#1F1808` at the bottom-right corner. Gold is used sparingly — only on the logo, primary CTAs, equity curves, the hero h1 emphasis line, the headline figure (1,482), and a few hairline accents. Everything else is restrained dark + warm off-white.

## Typography

- **Display:** Funnel Display (Pangram Pangram, via Google Fonts)
- **Body:** Hanken Grotesk (Google Fonts)
- **Data / mono:** JetBrains Mono (Google Fonts)
