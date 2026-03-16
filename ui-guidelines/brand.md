# Filament PHP — Brand Identity

**Scraped:** 2026-03-16 from https://filamentphp.com

---

## Logo

- **Primary Logo:** SVG format (`logo_1.svg` in assets/logos/)
- **Favicon:** Multiple sizes — 96x96 PNG, ICO, Apple touch icon
- **OG Image:** `logo_0.png` (used for social sharing previews)
- **Logo mark:** Appears to feature a geometric/abstract form — warm tone
- **Logo usage:** Appears in sticky nav (always visible) and in footer

---

## Color Story

Filament's palette is warm, artisan, and organic — intentionally avoiding the cold blues of typical developer tools.

| Role | Color | Story |
|---|---|---|
| **Primary** | `bone` / `cream` | Warm off-white parchment — approachable, crafted |
| **Accent** | `honey-200` (#efaf5d) | Golden amber — warmth, energy, highlights |
| **Dark** | `stone-800/900` | Rich near-black — serious, code-focused |
| **Green** | `minty` | Fresh, natural — community, growth, sponsors |
| **Blue** | `powder` | Tech/periwinkle — subtle, modern, code |
| **Specialty** | `bubblegum`, `flamingo`, `moon-mist` | Playful micro-accents for diversity |

**Key insight:** The palette evokes "handcrafted warmth meets developer precision" — neither corporate-cold (Bootstrap blues) nor trendy-dark (typical dev tools).

---

## Typography Personality

- **Outfit Variable** (Display): Geometric, rounded, modern — used for hero headlines. Conveys confidence and forward motion.
- **Albert Sans Variable** (Body): Humanist sans-serif — readable, friendly, approachable. Avoids clinical feel.
- **Roboto Mono Variable** (Code): Familiar developer font — signals technical precision in code demos.

**Tone:** Clean, confident, dev-community-native. Headlines use active, energetic language.

---

## Voice & Copy Tone

**Observed Headlines:**
- *"Build apps & admin panels fast, for your bright ideas."* — active, developer-first
- *"UI components"* — short, technical
- *"TALL Stack"* — community jargon embraced
- *"Turn PHP into polished UI"* — transformation narrative
- *"Trusted by the community"* — social proof, peer language

**CTA Patterns:**
- Verb-first: "Launch demo", "View docs", "Browse plugins", "Join us on Discord"
- Action-oriented: Never passive ("See our documentation" → always "View docs")
- Concise: max ~3 words for primary CTAs

**Heading Style:**
- Sentence case, not Title Case for most headings
- Short, punchy — rarely more than 6–7 words
- Occasionally uses line breaks as design elements (hero headline wraps for rhythm)

**What to Avoid:**
- Corporate jargon ("robust enterprise solution", "leverage synergies")
- Long explanatory CTAs ("Click here to learn more about our features")
- Cold or impersonal language — community warmth is core to brand

---

## Icon Style

- **Style:** Outline / line icons — not filled
- **Stroke:** Thin to medium weight (consistent with `Albert Sans` aesthetic)
- Custom icons for social (Twitter bird, Discord, GitHub, Mastodon)
- SVG sprites / inline SVGs used for performance
- Icon + label pattern in CTAs (arrow icon right-aligned)
- Arrow icon commonly used (`→` or chevron right) for directional CTAs

---

## Image Treatment

- **Format:** WebP preferred (observed in `image_*.webp` assets)
- **Hero images:** Full-width, likely product UI screenshots
- **Sponsor logos:** Displayed in horizontal marquee at equal height
- **Avatars/testimonials:** `rounded-full` circle crop, `size-11` (44px) standard
- **Border radius on images:** Match component context (full for avatars, lg for panels)
- **No heavy filters or overlays** on product imagery — let the UI speak for itself

---

## Brand Personality Summary

| Dimension | Filament |
|---|---|
| **Warmth** | High — organic palette, community-first language |
| **Technical Credibility** | High — code demos front and center, mono font, GitHub stars |
| **Playfulness** | Moderate — accents like bubblegum/flamingo hint at fun |
| **Formality** | Low-medium — developer casual, not enterprise |
| **Uniqueness** | High — warm palette stands out in PHP/Laravel ecosystem |
