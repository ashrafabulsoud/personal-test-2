# Filament PHP — Developer Handoff Guidelines

**Site:** https://filamentphp.com
**Scraped:** 2026-03-16
**Stack:** Laravel / TALL Stack (Tailwind, Alpine, Livewire, Laravel)
**CSS Framework:** Tailwind CSS v4 with custom design palette

---

## Color Palette

Filament uses a warm, organic custom palette layered on top of Tailwind's stone/amber defaults. Colors are defined as CSS custom properties using `oklch()` color space.

### Primary / Warm Neutrals

| Name | CSS Variable | Approx Hex | Usage |
|---|---|---|---|
| bone-100 | `--color-bone-100` | `#e6d6c4` | Primary borders, section dividers |
| bone-300 | `--color-bone-300` | `#d7bfa1` | Secondary borders, muted backgrounds |
| bone-500 | `--color-bone-500` | `#c4a882` | Muted text, decorative icons |
| cream-50 | `--color-cream-50` | `#faf4ec` | Very light warm section bg |
| cream-100 | `--color-cream-100` | `#f5ecdf` | Light card / panel backgrounds |
| serenade-50 | `--color-serenade-50` | `#fef6ed` | Hover background, subtle highlights |

### Accent — Honey (Amber/Golden)

| Name | CSS Variable | Approx Hex | Usage |
|---|---|---|---|
| honey-50 | `--color-honey-50` | `#fdf4e8` | Hover states |
| honey-100 | `--color-honey-100` | `#ffd6ab` | Tag backgrounds, warm highlights |
| honey-200 | `--color-honey-200` | `#efaf5d` | **Primary accent** — icons, highlights, CTAs |

### Accent — Powder (Blue/Periwinkle)

| Name | CSS Variable | Approx Hex | Usage |
|---|---|---|---|
| powder-200 | `--color-powder-200` | `#bfcfed` | Tech / code accent highlights |
| powder-300 | `--color-powder-300` | `#a8bce5` | Medium blue accent |
| powder-400 | `--color-powder-400` | `#8da8dc` | Stronger blue accent |

### Accent — Minty (Green)

| Name | CSS Variable | Approx Hex | Usage |
|---|---|---|---|
| minty-100 | `--color-minty-100` | `#bfe6d9` | Sponsor areas, positive/success states |
| minty-200 | `--color-minty-200` | `#b7dcd0` | Slightly richer green accent |

### Specialty Accents

| Name | CSS Variable | Approx Hex | Usage |
|---|---|---|---|
| cocoa | `--color-cocoa` | `#4a3728` | Deep warm brown accents |
| bubblegum | `--color-bubblegum` | `#f0b8d8` | Pink playful accent (badges) |
| flamingo | `--color-flamingo` | `#f5a89a` | Salmon/coral decorative |
| moon-mist-100 | `--color-moon-mist-100` | `#d9e2d0` | Soft sage/olive |

### Dark Neutrals (Stone Scale)

| Name | CSS Variable | Approx Hex | Usage |
|---|---|---|---|
| stone-100 | `--color-stone-100` | `#f9f9f8` | Text on dark backgrounds |
| stone-400 | `--color-stone-400` | `#a8a29e` | Placeholder, disabled |
| stone-500 | `--color-stone-500` | `#78716c` | Muted / secondary text |
| stone-600 | `--color-stone-600` | `#57534e` | Supporting body text |
| stone-700 | `--color-stone-700` | `#44403c` | Darker body text |
| stone-800 | `--color-stone-800` | `#292524` | Dark surfaces, nav, headings |
| stone-900 | `--color-stone-900` | `#1c1917` | Darkest bg — code blocks |

---

## Typography

### Font Families

| Role | Font | CSS Variable | Fallbacks |
|---|---|---|---|
| Display / Hero | Outfit Variable | `--font-outfit` | Albert Sans Variable, sans-serif |
| Body / UI | Albert Sans Variable | `--font-albert-sans` | Verdana, sans-serif |
| Code / Mono | Roboto Mono Variable | `--font-roboto-mono` | ui-monospace, Consolas, monospace |

All fonts are variable fonts (`font-display: swap`) loaded from `/build/assets/`.

### Font Weight Scale

| Token | Value | CSS Variable |
|---|---|---|
| Light | 300 | `--font-weight-light` |
| Normal | 400 | `--font-weight-normal` |
| Medium | 500 | `--font-weight-medium` |
| Semibold | 600 | `--font-weight-semibold` |
| Bold | 700 | `--font-weight-bold` |
| Black | 900 | `--font-weight-black` |

### Type Scale (Tailwind defaults)

| Class | Size | Typical Use |
|---|---|---|
| `text-xs` | 0.75rem / 12px | Labels, badges, meta |
| `text-sm` | 0.875rem / 14px | Secondary text, nav links |
| `text-base` | 1rem / 16px | Body copy |
| `text-lg` | 1.125rem / 18px | Lead paragraphs |
| `text-xl` | 1.25rem / 20px | Card headings |
| `text-2xl` | 1.5rem / 24px | Section subheadings |
| `text-3xl` | 1.875rem / 30px | Section headings |
| `text-4xl` | 2.25rem / 36px | Page headings |
| `text-5xl+` | 3rem+ | Hero headings (Outfit font) |

---

## Spacing System

**Base unit:** 4px (`--spacing` = 0.25rem)

### Section Padding Pattern (Responsive)

```
px-8 py-10          → mobile   (32px / 40px)
sm:px-10 sm:py-15   → tablet   (40px / 60px)
lg:px-15 lg:py-20   → desktop  (60px / 80px)
xl:pt-30            → xl       (120px top)
```

### Key Spacing Values

| Value | px | Use |
|---|---|---|
| `1.5` | 6px | Nav link padding-y |
| `2` / `2.5` | 8px / 10px | Nav link padding-x, icon gaps |
| `8` | 32px | Card padding (mobile) |
| `10` | 40px | Card padding (tablet) |
| `11` (`size-11`) | 44px | Avatar circle size |
| `15` | 60px | Desktop horizontal padding |
| `20` | 80px | Desktop section padding-y |

---

## Border Radius

| Class | Value | Use |
|---|---|---|
| `rounded-sm` | 2–4px | Subtle elements |
| `rounded-md` | 6px | Code labels, chips |
| `rounded-lg` | ~10px | Cards, panels |
| `rounded-xl` | ~14px | Larger containers |
| `rounded-full` | 9999px | **Primary CTA style** — pill buttons, avatars |

---

## Shadows & Effects

- **Glow effect:** `0 0 10px currentColor, 0 0 5px currentColor` — used for decorative hover glows
- **Inset border (dark surfaces):** `inset 0 0 0 1px rgb(255 255 255 / 0.1)`
- **Focus ring:** `focus-visible:ring` with `ring-black/50` or `ring-honey-200`
- **Backdrop blur:** `backdrop-blur-sm` on overlay elements

---

## Breakpoints

| Name | Breakpoint |
|---|---|
| `sm` | 640px |
| `md` | 768px |
| `lg` | 1024px |
| `xl` | 1280px |
| `2xl` | 1536px |
| `3xl` | 1650px |
| `4xl` | 2100px |

---

## CSS Variable Reference (Copy-Paste Ready)

```css
/* Custom Color Palette */
--color-bone-100: oklch(88.4245% .0300479 70.6911);   /* #e6d6c4 */
--color-bone-300: oklch(81.7249% .0488791 73.225);     /* #d7bfa1 */
--color-bone-500: oklch(70.3651% .0422809 73.2212);    /* #c4a882 */
--color-cream-50:  oklch(94.9635% .0271918 72.8095);   /* #faf4ec */
--color-cream-100: oklch(93.2102% .0290204 72.4687);   /* #f5ecdf */
--color-honey-50:  oklch(95.8608% .0271764 63.9586);   /* #fdf4e8 */
--color-honey-100: oklch(90.0675% .0724716 68.035);    /* #ffd6ab */
--color-honey-200: oklch(79.8191% .123963 71.1736);    /* #efaf5d */
--color-serenade-50: oklch(96.5417% .0239608 67.5384); /* #fef6ed */
--color-powder-200: oklch(82.4427% .0701426 263.296);  /* #bfcfed */
--color-powder-300: oklch(79.5844% .0821458 262.287);  /* #a8bce5 */
--color-powder-400: oklch(75.6824% .100319 260.281);   /* #8da8dc */
--color-minty-100: oklch(89.3447% .0443792 173.052);   /* #bfe6d9 */
--color-minty-200: oklch(86.4431% .042287 173.631);    /* #b7dcd0 */
--color-cocoa: oklch(33.9171% .0453791 73.2414);       /* #4a3728 */
--color-bubblegum: oklch(85.3521% .0835634 323.002);   /* #f0b8d8 */
--color-flamingo: oklch(81.5% .105659 13.7982);        /* #f5a89a */
--color-moon-mist-100: oklch(89.2112% .0199018 125.845); /* #d9e2d0 */

/* Stone Neutrals */
--color-stone-100: oklch(97% .001 106.424);   /* #f9f9f8 */
--color-stone-400: oklch(70.9% .01 56.259);   /* #a8a29e */
--color-stone-500: oklch(55.3% .013 58.071);  /* #78716c */
--color-stone-600: oklch(44.4% .011 73.639);  /* #57534e */
--color-stone-700: oklch(37.4% .01 67.558);   /* #44403c */
--color-stone-800: oklch(26.8% .007 34.298);  /* #292524 */
--color-stone-900: oklch(21.6% .006 56.043);  /* #1c1917 */

/* Typography */
--font-albert-sans: "Albert Sans Variable", Verdana, sans-serif;
--font-outfit: "Outfit Variable", "Albert Sans Variable", sans-serif;
--font-roboto-mono: "Roboto Mono Variable", ui-monospace, Consolas, monospace;
```
