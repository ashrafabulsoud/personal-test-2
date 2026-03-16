# Filament PHP — UX Flows & Interaction Patterns

**Scraped:** 2026-03-16 from https://filamentphp.com

---

## Navigation Patterns

### Top Navigation
- **Type:** Sticky horizontal navbar
- **Structure:** Logo (left) → Nav links → Social icons → GitHub stars (right)
- **Mobile:** Hamburger menu triggers full overlay navigation
- **Active state:** Current page link highlighted (e.g., "You're here" label for Home)
- **Hover:** `transition-all duration-300 ease-out` on all nav items; GitHub stars badge expands padding on hover (`hover:pr-4`)
- **Focus:** All interactive elements use `focus-visible:ring` for keyboard nav; never `focus:outline-none` alone

### In-Page Navigation
- Section-by-section scroll on homepage
- Docs pages use sidebar navigation (from `/docs` page observation)
- Anchor links within docs pages expected

### Breadcrumbs
- Not observed on marketing pages; likely in docs

---

## CTA Hierarchy

### Primary CTA — Pill Button
- **Shape:** `rounded-full` (pill)
- **Layout:** Full-width row with text left, arrow icon right (`justify-between`)
- **Hover:** Arrow icon slides right (`group-hover:translate-x-0.5`)
- **Examples:** "Launch demo", "Star us on GitHub", "View docs", "Sponsor Filament"
- **Dark variant:** `bg-stone-800 text-stone-100` for contrasting secondary action

### Announcement CTA
- **Shape:** `rounded-md` badge pill in header
- **Style:** `bg-stone-800` dark, with `text-honey-200` accent for version/label
- **Purpose:** Surface latest release or new feature

### Icon CTAs
- Social links (Twitter, Discord, GitHub, Mastodon) as icon-only square buttons
- Consistent sizing, ring focus, animated hover opacity

---

## Form Patterns

Not observed prominently on marketing pages. Docs search uses:
- **Search trigger:** Keyboard shortcut `⌘+K` (shown as badge in nav)
- **Input style:** Likely a modal/dialog with blurred overlay

---

## Feedback / Notification Patterns

- **Version badge:** Inline announcement in hero for new release (`bg-stone-800` pill)
- **GitHub star count:** Social proof prominently displayed in nav (`29.8K+`)
- **Focus rings:** Consistent `focus-visible:ring` feedback across all interactive elements
- **Hover transitions:** `duration-300 ease-out` throughout — no abrupt state changes

---

## Scroll Behaviors

- **Homepage:** Single long page with bordered section-by-section layout
- **Section dividers:** `border-b border-bone-100` creates clear vertical rhythm
- **Sponsor logos:** Horizontal scroll marquee with CSS gradient mask fade on edges
  ```
  mask-[linear-gradient(to_right,transparent,black_10%,black_90%,transparent)]
  ```
- **Dot pattern backgrounds:** Fixed or absolute positioned decorative overlays

---

## Accessibility Observations

- **Focus states:** `focus-visible:ring` applied consistently — keyboard users are well-served
- **Ring offset:** `focus-visible:ring-offset-2` used on icon buttons
- **Semantic HTML:** `<nav>`, `<header>`, `<section>`, `<main>` tags used correctly
- **Alt text:** Nav links use `aria-label` equivalent through text content
- **Skip links:** Not explicitly observed, but nav ordering is logical
- **Color contrast:** `text-stone-800` (#292524) on `bg-cream-100` (#f5ecdf) provides strong contrast
- **Font:** Variable fonts with `font-display: swap` for performance
- **Keyboard shortcut:** `⌘+K` for search shown in UI

---

## Page Layout Structure

### Homepage Layout Flow
```
[Sticky Nav]
[Hero — full width, pt-20, border-b border-bone-100]
[Feature: UI Components — @container grid]
[Feature: TALL Stack — 2-col grid]
[Feature: Turn PHP into polished UI]
[Sponsors — horizontal marquee]
[Trusted by community — testimonials]
[Footer]
```

### Section Pattern
Every major section:
1. `border-b border-bone-100` bottom divider
2. Responsive padding: `px-8 py-10 sm:px-10 sm:py-15 lg:px-15 lg:py-20`
3. `@container` for inner content responsiveness (where applicable)

---

## Animation Conventions

| Pattern | Implementation |
|---|---|
| Default transition | `transition-all duration-300 ease-out` |
| Fast transition | `transition duration-200` |
| Transform animations | `will-change-transform` declared up-front |
| Arrow icon hover | `group-hover:translate-x-0.5` |
| Sponsor marquee | CSS animation (infinite scroll) |
| Background glows | `0 0 10px currentColor` box-shadow |

---

## Dark vs Light Surfaces

The site uses a **dual-surface strategy**:

| Surface | Background | Text | Use Case |
|---|---|---|---|
| Light (default) | `bg-cream-100` / `bg-bone-100` | `text-stone-800` | Marketing sections |
| Neutral light | `bg-serenade-50` | `text-stone-800` | Card panels |
| Dark | `bg-stone-800` | `text-stone-100` | Code demos, announcement pills |
| Darkest | `bg-stone-900` | `text-stone-100` | Code blocks |

**Key rule:** Dark sections (`bg-stone-800+`) always use `text-stone-100` or `text-cream-100`, never raw `text-white`.
