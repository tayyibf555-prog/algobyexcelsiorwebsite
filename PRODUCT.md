# Product

## Register

brand

## Users

UK-based retail traders, ages 25–45, with disposable capital and an existing TradingView/broker setup. Most have been burned at least once by a "trading guru", a Telegram pump signal, or an Instagram bot promising passive income. They are sceptical, time-poor, and read every site through a fraud filter. Their first decision in the first three seconds is *"is this real?"*. If the site fails that test, no amount of copy fixes it.

The visitor's only meaningful action on the page is to book a free 15-minute consultation. They will not pay from a landing page. They expect to speak to a human before any money changes hands.

## Product Purpose

Algo by Excelsior is a fully automated, mechanical trading system that executes trades on Nasdaq and Gold via TradingView with no manual intervention. Built and operated by a working trader in Glasgow.

The site has one job: convince a sceptical, sophisticated retail trader that this is a legitimate, premium, owner-operated product, then convert them to a free 15-minute discovery call. Success is bookings, not signups.

## Brand Personality

Three concrete brand-voice words: *quiet · accountable · operator-grade*.

Voice is closer to Mercury Bank or Wise than to a trading guru. Confident, direct, evidentially-grounded. Short sentences. No hype words. No exclamation marks. No emoji. The brand is comfortable being boring next to a Telegram pump group, because boring is the point — boring is what an institution looks like.

The audience reads emotional restraint as competence. They read excitement as a tell.

## Anti-references

What this must NOT look like:

- Telegram pump groups, Discord signal services, Instagram trading bots, "passive income" creators
- Generic SaaS landing-page templates (Tailwind UI, Hero + 3 feature cards + pricing + CTA)
- Crypto-bro dark mode with neon green candlesticks, glowing UI, holographic robot mascots
- 3D cyberpunk dashboards, NFT-style hero gradients, "futuristic" sci-fi tropes
- Generic AI-generated landing aesthetic: gradient-text section labels, glassmorphism on every surface, identical 3-card grids, hero-metric template (big number + small label + supporting stats)
- Editorial-magazine costume on a fintech brief — Fraunces-italic display + Klim-style ruled separators + lowercase mono labels — currently a saturated AI default lane
- Any motion, copy or imagery that signals "easy money" or "passive"

Reference points (specific, real): institutional reporting layouts (Financial Times Markets pages, Bloomberg Terminal data graphics), Stripe and Mercury for marketing restraint, Linear for product surface polish, Robinhood Gold tier for committed dark-mode fintech.

## Design Principles

1. **Show, don't tell.** Verified data and real screen captures beat marketing claims at every fold. The audience trusts evidence; copy without evidence reads as a pitch.
2. **Restraint signals competence.** The page should feel quieter than its category, not louder. If a treatment makes the page feel like it's trying, cut it.
3. **The trader runs the brand.** Faces, signatures, real names, real Glasgow specifics. The "no salespeople, direct founder access" claim must be visible on the surface, not just stated in copy.
4. **Specific over generic, every time.** "Live for 1,127 days · 99.92% uptime" beats "battle-tested". "Last trade closed 17 minutes ago" beats "real-time execution". The detail is the differentiator.
5. **Compliance is design.** FCA-friendly disclaimers, plausible performance figures, and "book a call" (never "buy now") are not legal afterthoughts — they're trust signals visible in the layout itself.

## Accessibility & Inclusion

WCAG AA on contrast for body text on the dark canvas (light text needs +0.05–0.1 line-height; already in CSS). All decorative animation gated behind `prefers-reduced-motion: reduce`. Semantic HTML landmarks (`<header>`, `<main>`, `<section>`, `<footer>`) with descriptive `aria-label`s on icon-only controls. Focus rings visible in the violet brand colour. Hero video is muted, looped, captioned by adjacent copy, and never carries information that copy doesn't also state. Numeric data uses `font-variant-numeric: tabular-nums` so digits align in columns.
