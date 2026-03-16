# Design System Guide
**Source:** https://filamentphp.com (scraped 2026-03-16)
**Framework:** Tailwind CSS v4 with custom warm organic palette

> This guide is auto-loaded by Claude Code. Reference it for all UI work in this project.

---

## 1. Color Palette + CSS Variables

Filament uses a warm, artisan palette — not the cold blues of typical dev tools. Colors are in `oklch()` color space.

### Custom Palette

| Name | CSS Variable | Approx Hex | When to Use |
|---|---|---|---|
| `bone-100` | `--color-bone-100` | `#e6d6c4` | Section borders, dividers (`border-bone-100`) |
| `bone-300` | `--color-bone-300` | `#d7bfa1` | Muted backgrounds, secondary borders |
| `bone-500` | `--color-bone-500` | `#c4a882` | Decorative accents, muted icons |
| `cream-50` | `--color-cream-50` | `#faf4ec` | Very light warm page background |
| `cream-100` | `--color-cream-100` | `#f5ecdf` | Card and panel backgrounds |
| `honey-50` | `--color-honey-50` | `#fdf4e8` | Hover state backgrounds |
| `honey-100` | `--color-honey-100` | `#ffd6ab` | Tag backgrounds, warm chip highlights |
| `honey-200` | `--color-honey-200` | `#efaf5d` | **Primary accent** — icons, highlights, badge text |
| `serenade-50` | `--color-serenade-50` | `#fef6ed` | Alternate light section bg, nav highlight |
| `powder-200` | `--color-powder-200` | `#bfcfed` | Blue/tech accents, code highlights |
| `powder-300` | `--color-powder-300` | `#a8bce5` | Medium blue accent |
| `powder-400` | `--color-powder-400` | `#8da8dc` | Stronger blue accent |
| `minty-100` | `--color-minty-100` | `#bfe6d9` | Community/sponsor areas, success states |
| `minty-200` | `--color-minty-200` | `#b7dcd0` | Slightly richer green accent |
| `cocoa` | `--color-cocoa` | `#4a3728` | Deep warm brown, dark decorative elements |
| `bubblegum` | `--color-bubblegum` | `#f0b8d8` | Playful pink micro-accents |
| `flamingo` | `--color-flamingo` | `#f5a89a` | Salmon/coral decorative touches |
| `moon-mist-100` | `--color-moon-mist-100` | `#d9e2d0` | Soft sage/olive accents |

### Stone Scale (Dark Neutrals)

| Name | CSS Variable | Approx Hex | When to Use |
|---|---|---|---|
| `stone-100` | `--color-stone-100` | `#f9f9f8` | Text/content on dark surfaces |
| `stone-400` | `--color-stone-400` | `#a8a29e` | Placeholder text, disabled states |
| `stone-500` | `--color-stone-500` | `#78716c` | Muted secondary text |
| `stone-600` | `--color-stone-600` | `#57534e` | Supporting body text |
| `stone-700` | `--color-stone-700` | `#44403c` | Darker body text |
| `stone-800` | `--color-stone-800` | `#292524` | Dark surfaces, nav bar, primary headings on light bg |
| `stone-900` | `--color-stone-900` | `#1c1917` | Darkest — code blocks, deep dark panels |

### CSS Variables (Copy-Paste)
```css
--color-bone-100: oklch(88.4245% .0300479 70.6911);
--color-bone-300: oklch(81.7249% .0488791 73.225);
--color-bone-500: oklch(70.3651% .0422809 73.2212);
--color-cream-50:  oklch(94.9635% .0271918 72.8095);
--color-cream-100: oklch(93.2102% .0290204 72.4687);
--color-honey-50:  oklch(95.8608% .0271764 63.9586);
--color-honey-100: oklch(90.0675% .0724716 68.035);
--color-honey-200: oklch(79.8191% .123963 71.1736);
--color-serenade-50: oklch(96.5417% .0239608 67.5384);
--color-powder-200: oklch(82.4427% .0701426 263.296);
--color-powder-300: oklch(79.5844% .0821458 262.287);
--color-powder-400: oklch(75.6824% .100319 260.281);
--color-minty-100: oklch(89.3447% .0443792 173.052);
--color-minty-200: oklch(86.4431% .042287 173.631);
--color-stone-100: oklch(97% .001 106.424);
--color-stone-400: oklch(70.9% .01 56.259);
--color-stone-500: oklch(55.3% .013 58.071);
--color-stone-600: oklch(44.4% .011 73.639);
--color-stone-700: oklch(37.4% .01 67.558);
--color-stone-800: oklch(26.8% .007 34.298);
--color-stone-900: oklch(21.6% .006 56.043);
--font-albert-sans: "Albert Sans Variable", Verdana, sans-serif;
--font-outfit: "Outfit Variable", "Albert Sans Variable", sans-serif;
--font-roboto-mono: "Roboto Mono Variable", ui-monospace, Consolas, monospace;
```

---

## 2. Typography Rules

### Font Families

| Font | Variable | Fallbacks | Use For |
|---|---|---|---|
| **Outfit Variable** | `--font-outfit` | Albert Sans Variable, sans-serif | Hero headlines, display text, large headings |
| **Albert Sans Variable** | `--font-albert-sans` | Verdana, sans-serif | Body copy, UI labels, nav, subheadings |
| **Roboto Mono Variable** | `--font-roboto-mono` | ui-monospace, Consolas | Code snippets, version numbers, technical labels |

### Type Scale

| Tailwind Class | Size | Use |
|---|---|---|
| `text-xs` | 12px | Labels, badges, language tags, meta |
| `text-sm` | 14px | Nav links, secondary text, code labels |
| `text-base` | 16px | Body copy default |
| `text-lg` | 18px | Lead paragraphs, important callouts |
| `text-xl` | 20px | Card titles, feature headings |
| `text-2xl` | 24px | Section subheadings |
| `text-3xl–4xl` | 30–36px | Section headings (`text-stone-800`) |
| `text-5xl+` | 48px+ | Hero headlines (always Outfit font, `font-black`) |

### Rules
- **Hero headlines:** Always `font-outfit font-black` — never Albert Sans for display
- **Body text:** `text-stone-600` to `text-stone-800` on light backgrounds
- **On dark surfaces:** Use `text-stone-100` or `text-cream-100` — never raw `text-white`
- **Code/version labels:** Always `font-roboto-mono text-xs`
- **Never** use `font-weight` below 400 on any text
- **Never** use pure `#000000` black for text — use `text-stone-900` at darkest

---

## 3. Component Patterns — Do's & Don'ts

### Buttons / CTAs
**Do:**
- Use `rounded-full` pill shape for all primary CTAs
- Include a right-arrow icon (`→`) with `group-hover:translate-x-0.5`
- Use `justify-between` to push text left, icon right
- Apply `transition-all duration-300 ease-out` on all interactive buttons
- Dark CTAs: `bg-stone-800 text-stone-100`; Light CTAs: `bg-cream-100 text-stone-900`

**Don't:**
- Don't use square-cornered buttons for primary actions
- Don't use `bg-white` — always use the warm palette (`cream-100`, `serenade-50`)
- Don't omit focus states — always include `focus-visible:ring`

```html
<!-- Correct primary CTA -->
<a class="group inline-flex items-center justify-between rounded-full
           font-medium text-stone-900 bg-cream-100 hover:bg-honey-50
           px-5 py-2.5 transition-all duration-300 ease-out
           focus:outline-none focus-visible:ring">
  View docs
  <span class="group-hover:translate-x-0.5 transition-transform">→</span>
</a>
```

### Cards / Feature Sections
**Do:**
- Use `border-b border-bone-100` to divide sections
- Apply responsive padding: `px-8 py-10 sm:px-10 sm:py-15 lg:px-15 lg:py-20`
- Use `bg-cream-100` or `bg-serenade-50` for card backgrounds

**Don't:**
- Don't use `bg-gray-*` or `bg-neutral-*` — always the custom warm palette
- Don't skip the responsive padding pattern — be consistent across sections

### Code Blocks
**Do:**
- Background: `bg-stone-900`
- Text: `text-stone-100` with `font-roboto-mono`
- Language label: `bg-stone-800 text-xs font-roboto-mono` with asymmetric radius (`rounded-tl-md rounded-tr-md rounded-br-md`)
- Padding: `p-8 sm:p-10`

**Don't:**
- Don't use `bg-gray-900` — use `bg-stone-900`
- Don't use `font-mono` without the `font-roboto-mono` custom class

### Navigation
**Do:**
- Nav links: `group relative inline-grid place-items-center px-2 py-1.5 transition-all duration-300 ease-out will-change-transform`
- Always include `focus-visible:ring` for keyboard access

**Don't:**
- Don't style nav links as buttons — they're text links with animated indicators

### Badges / Tags
**Do:**
- "New" badge: `bg-honey-200 text-stone-900 rounded text-xs font-semibold px-1 py-0.5`
- Version/announcement: `bg-stone-800 text-stone-100 rounded-md text-sm`

---

## 4. Spacing & Layout System

### Base Unit
`4px` (Tailwind spacing scale — `spacing-1` = 4px)

### Section Padding (Always Use This Pattern)
```
px-8 py-10                          ← mobile (32px / 40px)
sm:px-10 sm:py-15                   ← tablet (40px / 60px)
lg:px-15 lg:py-20                   ← desktop (60px / 80px)
xl:pt-30                            ← xl only, top padding (120px)
```

### Grid System
- Two-column desktop layouts: `grid grid-cols-1 lg:grid-cols-2`
- Use `@container` on sections that need inner content responsiveness
- Section dividers: `border-b border-bone-100` (not `border-gray-*`)

### Key Component Sizes
| Component | Size |
|---|---|
| Avatar circle | `size-11` (44px) |
| Nav link padding | `px-2 py-1.5` (8px / 6px) |
| Card padding | `p-8 sm:p-10` |
| Button gap (icon) | `gap-1.5` to `gap-2.5` |

### Spacing Steps
- `1.5` (6px): Tight icon/text gaps
- `2–2.5` (8–10px): Small component padding
- `4` (16px): Standard element spacing
- `8` (32px): Card padding mobile
- `10` (40px): Card padding tablet / section vertical
- `15` (60px): Desktop horizontal section padding
- `20` (80px): Desktop vertical section padding
- `30` (120px): XL hero top padding

---

## 5. Tone & Copy Style

**Voice:** Developer-native, community-first, confident but not corporate.

**Adjectives describing the voice:** Direct, energetic, warm, peer-to-peer

### CTA Patterns
- Always **verb-first**: "View docs" not "Documentation"; "Launch demo" not "See a demo"
- **Active voice**: "Build apps fast" not "Apps can be built faster"
- **Short**: Primary CTAs max 3–4 words; secondary CTAs max 6 words

### Heading Style
- **Sentence case** (not Title Case): "Build apps fast" not "Build Apps Fast"
- Short, punchy — rarely more than 7 words
- Accent key words with color (`text-honey-200`) or gradient, not quotation marks

### Things to Avoid in Copy
- Corporate jargon: "robust", "enterprise-grade", "leverage", "synergies"
- Passive constructions: "can be used to", "is designed for"
- Verbose CTAs: "Click here to learn more about our documentation"
- Cold/clinical language — always maintain community warmth

---

## 6. Icon & Image Style

### Icons
- **Style:** Outline / line icons — not filled
- **Weight:** Medium stroke, consistent with Albert Sans font personality
- SVG preferred, inline for critical icons (performance)
- Arrow icon (`→` or chevron right) used consistently for CTAs and directional links

### Sizing
- Navigation icons: ~20px
- CTA inline icons: match text size
- Avatar/feature icons: 44px container (`size-11`)

### Images
- **Format:** WebP preferred
- **Avatar treatment:** `rounded-full overflow-hidden size-11` — always circular
- **Product screenshots:** No filters; let the UI speak
- **Sponsor logos:** Uniform height, grayscale on default, color on hover (likely)
- **Aspect ratios:** Maintain natural — no stretching
- **Object-fit:** `object-cover` for fixed-size image containers

### Do's & Don'ts for Imagery
- Do use WebP for all raster images
- Do use `rounded-full` for person avatars
- Don't add heavy drop shadows to product screenshots
- Don't use stock photography — real UI screenshots and community photos only
- Don't use images without alt text

---

## Quick Reference

### Most-Used Classes
```
/* Backgrounds */
bg-cream-100    bg-serenade-50    bg-stone-800    bg-stone-900
bg-honey-50     bg-bone-100       bg-minty-100/30

/* Text */
text-stone-800  text-stone-600   text-stone-100  text-honey-200  text-bone-300

/* Borders */
border-bone-100   border-honey-200

/* Spacing */
px-8 py-10 sm:px-10 sm:py-15 lg:px-15 lg:py-20

/* Shapes */
rounded-full   rounded-md   rounded-lg

/* Transitions */
transition-all duration-300 ease-out

/* Focus */
focus:outline-none focus-visible:ring focus-visible:ring-black/50
```

### Full Handoff Package
See `./ui-guidelines/` for:
- `guidelines.md` — full color/typography reference
- `design-tokens.json` — structured token data
- `components.md` — HTML patterns for each component
- `ux-flows.md` — interaction & accessibility patterns
- `brand.md` — voice, copy, brand identity
- `assets/` — logos, images, CSS files
