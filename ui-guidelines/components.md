# Filament PHP — UI Component Inventory

**Scraped:** 2026-03-16 from https://filamentphp.com

---

## 1. Navigation Bar

**Description:** Sticky horizontal top nav on a warm light background. Contains logo, nav links, social icons, and a prominent GitHub star count badge.

**HTML Structure:**
```html
<header>
  <nav>
    <!-- Logo (SVG) -->
    <a href="/"><!-- logo svg --></a>

    <!-- Nav Links -->
    <a class="group relative inline-grid place-items-center px-2 py-1.5
              transition-all duration-300 ease-out will-change-transform
              focus:outline-none focus-visible:ring">
      Docs
    </a>

    <!-- GitHub Stars Badge -->
    <a class="group flex items-center gap-2.5 pr-3 pb-0.5 whitespace-nowrap
              transition-all duration-300 ease-out hover:pr-4">
      29.8K+ GitHub stars
    </a>

    <!-- Social Icons (Twitter, Discord, GitHub, Mastodon) -->
    <a class="group relative inline-grid place-items-center
              transition duration-300 ease-out focus:outline-none focus-visible:ring">
      <!-- SVG icon -->
    </a>
  </nav>
</header>
```

**Key CSS Classes:**
- Nav links: `group relative inline-grid place-items-center px-2 py-1.5 transition-all duration-300 ease-out`
- GitHub badge: animated `hover:pr-4` expansion
- Mobile: hamburger menu with `MenuNavigation menu` label

**Usage Notes:**
- Uses `will-change-transform` on nav items for smooth hover animations
- Focus states: `focus-visible:ring` pattern throughout
- Mobile nav is a full overlay menu

---

## 2. Hero Section

**Description:** Large full-width section with big display headline, sub-copy, two CTA buttons, and decorative elements.

**HTML Structure:**
```html
<section class="border-b border-bone-100 pt-20">
  <h1 class="font-outfit font-black text-stone-900">
    Build apps & admin panels <span>fast</span>, for your <span>bright ideas.</span>
  </h1>
  <p class="text-stone-600">...</p>

  <!-- Primary CTAs — Pill Buttons -->
  <div>
    <a class="group inline-flex w-full items-center justify-between
              rounded-full font-medium whitespace-nowrap text-stone-900
              transition-all duration-300 ease-out">
      Launch demo
      <!-- Arrow icon -->
    </a>
    <a class="... bg-stone-800 text-stone-100 ...">
      Star us on GitHub
    </a>
  </div>

  <!-- Announcement Banner -->
  <div class="group flex items-center gap-2 overflow-hidden bg-stone-800
              py-2.75 pr-3.75 pl-3 text-sm whitespace-nowrap text-stone-100 rounded-md">
    New version v5 · View release page
  </div>
</section>
```

**Key CSS Classes:**
- Section: `border-b border-bone-100 pt-20`
- Headline: Outfit font, `font-black`, very large size
- Accent words: gradient or `text-honey-200` color treatment
- CTAs: `rounded-full` pill shape with icon on right

---

## 3. Pill CTA Button

**Description:** The dominant interactive element. Rounded-full pill shape with arrow icon aligned right. Two variants: light (default) and dark.

**Light Variant:**
```html
<a class="group inline-flex w-full items-center justify-between
           rounded-full font-medium whitespace-nowrap text-stone-900
           bg-cream-100 hover:bg-honey-50
           transition-all duration-300 ease-out px-4 py-2.5">
  <span>Launch demo</span>
  <span class="group-hover:translate-x-0.5 transition-transform">→</span>
</a>
```

**Dark Variant:**
```html
<a class="... bg-stone-800 text-stone-100 hover:bg-stone-900 ...">
  Star us on GitHub
</a>
```

**Usage Notes:**
- Always use `rounded-full` for pill shape
- Arrow icon animates right on hover via `group-hover:translate-x-0.5`
- Never use square corners on primary CTAs

---

## 4. Announcement / Version Badge

**Description:** Compact pill-shaped badge announcing new features/versions. Used in header area.

```html
<a class="group flex items-center gap-2 overflow-hidden
           bg-stone-800 py-2.75 pr-3.75 pl-3
           text-sm whitespace-nowrap text-stone-100 rounded-md">
  <span class="text-honey-200">New version</span>
  <span class="text-stone-400">v5</span>
  <span>View release page</span>
  <!-- Arrow icon -->
</a>
```

**Key Classes:** `bg-stone-800 text-stone-100 rounded-md gap-2`

---

## 5. Feature Section (Bordered Grid Cell)

**Description:** Each feature is a bordered section with consistent padding. Sections stack vertically on mobile, form a grid on desktop. A `border-b border-bone-100` divides each section.

```html
<section class="@container border-b border-bone-100 px-8 py-10 sm:px-10 sm:py-15 lg:px-15 lg:py-20">
  <h2 class="text-stone-800 font-semibold">UI components</h2>
  <p class="text-stone-600">...</p>
  <!-- Feature content / code demo -->
</section>
```

**Key Pattern:**
- Border: `border-b border-bone-100`
- Padding: responsive `px-8 py-10 → sm:px-10 sm:py-15 → lg:px-15 lg:py-20`
- Two-column grid: `grid grid-cols-1 lg:grid-cols-2`
- Container queries: `@container` for inner responsive adjustments

---

## 6. Code Block / Demo Panel

**Description:** Dark-themed code preview panel with language label, used inline within feature sections.

```html
<div class="bg-stone-900 p-8 sm:p-10 rounded-lg">
  <!-- Language label (top-left tab) -->
  <div class="absolute top-0 left-0 z-2 bg-stone-800 px-2 pt-px pb-0.5
               font-roboto-mono text-xs text-stone-100
               rounded-tl-md rounded-tr-md rounded-br-md">
    PHP
  </div>

  <!-- Code content -->
  <code class="font-roboto-mono text-stone-100">...</code>
</div>
```

**Key Classes:**
- Container: `bg-stone-900 p-8 sm:p-10`
- Language tab: `bg-stone-800 font-roboto-mono text-xs` with asymmetric border-radius (chat bubble style)
- Text: `text-stone-100` on dark background

---

## 7. Sponsor Logo Area

**Description:** Horizontal scrolling marquee of sponsor logos. "Your logo here" placeholder uses a dashed border with mint background.

```html
<section class="border-b border-bone-100 px-8 py-10 sm:px-10 sm:py-15 lg:px-15 lg:py-20">
  <h2>Sponsors</h2>
  <!-- Logos with mask gradient fade -->
  <div class="mask-[linear-gradient(to_right,transparent,black_10%,black_90%,transparent)]">
    <!-- Sponsor logos -->
  </div>

  <!-- CTA placeholder -->
  <a class="custom-dashed-border group bg-minty-100/30 overflow-hidden
             transition duration-300 rounded-md">
    Your logo here
  </a>
</section>
```

---

## 8. Testimonial / Community Avatar

**Description:** Circular avatar with fallback initials. Used in testimonials / community section.

```html
<div class="relative isolate grid shrink-0 place-items-center
             overflow-hidden rounded-full size-11 bg-stone-900 text-cream-100">
  <!-- img or initials fallback -->
</div>
```

**Key Classes:** `rounded-full size-11 bg-stone-900 text-cream-100`

---

## 9. Navigation Link (Inline With Underline Hover)

**Description:** Used in both top nav and footer. Animated hover state with transform.

```html
<a class="group relative inline-grid place-items-center
           transition-all duration-300 ease-out will-change-transform
           focus:outline-none focus-visible:ring focus-visible:ring-black/50">
  <span class="group-hover:opacity-0">Docs</span>
  <!-- Animated underline or hover indicator -->
</a>
```

---

## 10. Social / Icon Button

**Description:** Square icon-only button for social links. Consistent sizing with ring focus state.

```html
<a class="group relative inline-grid place-items-center
           transition duration-300 ease-out
           focus:outline-none focus-visible:ring focus-visible:ring-black/50
           focus-visible:ring-offset-2 rounded-md">
  <svg><!-- icon --></svg>
</a>
```

---

## 11. Background Dot Pattern Overlay

**Description:** Decorative full-coverage dot pattern used on hero and overlay sections.

```html
<div class="bg-dots-pattern absolute inset-0 bg-black/21 bg-repeat backdrop-blur-sm"></div>
```

**Custom Class:** `bg-dots-pattern` — defined in `app-BJNxUIvr.css` as a CSS background pattern.

---

## 12. "New" Badge Tag

**Description:** Small inline label for new features (e.g., "Custom Dashboards**New**").

```html
<span class="ml-1 rounded bg-honey-200 px-1 py-0.5 text-xs font-semibold text-stone-900">
  New
</span>
```

**Key Classes:** `bg-honey-200 rounded text-xs font-semibold`
