# Kala Studios Design System & Development Rules

## Brand Identity

- **Name:** Kala Studios (stylized: KALA STUDIOS)
- **Founded by:** Kov Rastogi
- **Tagline:** Bespoke Digital Infrastructure & AI Automation.
- **Etymology:** "Kala" (Hindi/Sanskrit) means "Art" or "Skill." Its deeper roots in the 64 Kalās encompass everything from design and architecture to logic and mathematics.
- **Domain:** kalastudio.ai
- **Aesthetic:** Ultra-premium, dark/cyber, architectural precision ("The AKSHA philosophy")
- **Mission:** Bridge aesthetic excellence and technical infrastructure. Transform static businesses into automated, self-scaling digital entities.
- **Type:** AI Growth Agency (done-for-you services, not SaaS)
- **Core Differentiator:** We build proprietary "Growth Systems" (WaaS + managed AI), not websites. Clients don't get CMS access — we control the environment.

### Clients

| Client | Owner | Description |
|---|---|---|
| Measure Joy | Christian Velasquez | Curated vintage camera brand. Kala Studios built a custom e-commerce platform for them. |

---

## 1. Design Tokens

All tokens are defined as CSS custom properties on `:root` in `index.html`.

### Colors

```css
:root {
  /* ── Core Brand ── */
  --color-black:        #050505;
  --color-white:        #fafafa;

  /* ── Surface / Background ── */
  --surface-primary:    #050505;   /* page bg */
  --surface-elevated:   #0a0a0a;   /* cards, panels */
  --surface-overlay:    #111111;   /* modals, dropdowns */
  --surface-subtle:     rgba(255, 255, 255, 0.03);  /* glass cards */

  /* ── Border ── */
  --border-default:     rgba(255, 255, 255, 0.08);
  --border-hover:       rgba(255, 255, 255, 0.16);
  --border-accent:      rgba(123, 57, 252, 0.3);

  /* ── Accent — Purple (Primary Action) ── */
  --accent-primary:     #7b39fc;
  --accent-primary-hover: #8b4dff;
  --accent-glow:        rgba(123, 57, 252, 0.4);
  --accent-subtle:      rgba(123, 57, 252, 0.08);

  /* ── Accent — Gold (Premium / Highlight) ── */
  --accent-gold:        #c9a84c;
  --accent-gold-subtle: rgba(201, 168, 76, 0.12);

  /* ── Text ── */
  --text-primary:       #fafafa;
  --text-secondary:     rgba(255, 255, 255, 0.55);
  --text-muted:         rgba(255, 255, 255, 0.35);
  --text-accent:        #c4a1ff;

  /* ── Semantic ── */
  --color-success:      #34d399;
  --color-warning:      #fbbf24;
  --color-error:        #f87171;

  /* ── Gradients ── */
  --gradient-headline:  linear-gradient(135deg, #fff 30%, #c4a1ff 70%, #7b39fc 100%);
  --gradient-card-border: linear-gradient(135deg, rgba(123,57,252,0.2), transparent 40%, transparent 60%, rgba(168,85,247,0.15));
  --gradient-orb-1:     radial-gradient(circle, #7b39fc 0%, transparent 70%);
  --gradient-orb-2:     radial-gradient(circle, #4f1dba 0%, transparent 70%);
  --gradient-orb-3:     radial-gradient(circle, #2d1a6e 0%, transparent 70%);
}
```

### Typography

```css
:root {
  /* ── Font Families ── */
  --font-display:   'Inter', sans-serif;         /* Headlines */
  --font-serif:     'Instrument Serif', serif;    /* Italic accent headlines */
  --font-body:      'Manrope', sans-serif;        /* Body, UI, nav */

  /* ── Font Sizes (fluid where possible) ── */
  --text-xs:    12px;
  --text-sm:    13px;
  --text-base:  15px;
  --text-md:    18px;
  --text-lg:    24px;
  --text-xl:    32px;
  --text-2xl:   48px;
  --text-hero:  clamp(40px, 6vw, 80px);

  /* ── Font Weights ── */
  --weight-regular:  400;
  --weight-medium:   500;
  --weight-semibold: 600;
  --weight-bold:     700;

  /* ── Line Heights ── */
  --leading-tight:   1.05;
  --leading-snug:    1.2;
  --leading-normal:  1.5;
  --leading-relaxed: 1.6;

  /* ── Letter Spacing ── */
  --tracking-tight:  -0.03em;   /* Headlines */
  --tracking-normal: 0;
  --tracking-wide:   0.02em;    /* Badges, labels */
  --tracking-wider:  0.08em;    /* All-caps labels */
  --tracking-widest: 0.15em;    /* Logotype, section labels */
}
```

### Spacing

```css
:root {
  --space-1:  4px;
  --space-2:  8px;
  --space-3:  12px;
  --space-4:  16px;
  --space-5:  20px;
  --space-6:  24px;
  --space-8:  32px;
  --space-10: 40px;
  --space-12: 48px;
  --space-16: 64px;
  --space-20: 80px;
  --space-24: 96px;
  --space-32: 128px;
}
```

### Radius

```css
:root {
  --radius-sm:   8px;
  --radius-md:   12px;
  --radius-lg:   16px;
  --radius-xl:   20px;
  --radius-2xl:  24px;
  --radius-full: 9999px;
}
```

### Shadows & Effects

```css
:root {
  --shadow-glow-sm:  0 0 16px var(--accent-glow);
  --shadow-glow-md:  0 0 32px var(--accent-glow);
  --shadow-glow-lg:  0 0 48px var(--accent-glow);
  --blur-orb:        120px;
  --blur-glass:      16px;
}
```

---

## 2. Component Patterns

### Architecture

This is a **static HTML/CSS site** (no JS framework). Components are built as semantic HTML blocks with BEM-influenced class naming.

### Naming Convention

```
.[section]-[element]           → .hero-headline, .nav-logo
.[section]-[element]--[mod]    → .btn--primary, .btn--ghost
.[utility]                     → .glass-card, .gradient-text
```

### Core Components

| Component | Class | Description |
|---|---|---|
| Glass Card | `.glass-card` | Frosted panel: `background: var(--surface-subtle)`, `border: 1px solid var(--border-default)`, `backdrop-filter: blur(var(--blur-glass))` |
| Primary Button | `.btn--primary` | Purple fill, white text, glow on hover |
| Ghost Button | `.btn--ghost` | Transparent bg, subtle border, white text |
| Badge Pill | `.hero-badge` | Rounded pill with pulsing dot indicator |
| Section Label | `.section-label` | All-caps, tracked-out, muted small text |
| Gradient Headline | `.gradient-text` | `background: var(--gradient-headline); -webkit-background-clip: text; -webkit-text-fill-color: transparent;` |

### Button Patterns

```css
/* Primary */
.btn--primary {
  font-family: var(--font-body);
  font-weight: var(--weight-semibold);
  font-size: var(--text-base);
  color: #fff;
  background: var(--accent-primary);
  border: none;
  border-radius: var(--radius-md);
  padding: 16px 32px;
  cursor: pointer;
  transition: all 0.25s ease;
}
.btn--primary:hover {
  background: var(--accent-primary-hover);
  box-shadow: var(--shadow-glow-md), 0 8px 32px rgba(123,57,252,0.25);
  transform: translateY(-2px);
}

/* Ghost */
.btn--ghost {
  color: rgba(255,255,255,0.8);
  background: var(--surface-subtle);
  border: 1px solid var(--border-default);
  border-radius: var(--radius-md);
  padding: 16px 32px;
}
.btn--ghost:hover {
  color: #fff;
  background: rgba(255,255,255,0.1);
  border-color: var(--border-hover);
  transform: translateY(-2px);
}
```

---

## 3. Frameworks & Build

| Aspect | Value |
|---|---|
| Framework | None (vanilla HTML/CSS) |
| Styling | Inline `<style>` in `index.html` using CSS custom properties |
| Build system | None — static file served directly |
| Hosting | Vercel (Git integration, auto-deploys on push to `main`) |
| Fonts | Google Fonts: Inter, Instrument Serif, Manrope |

### Future migration path
If the site grows beyond a single page, extract to:
- `/styles/tokens.css` — design tokens
- `/styles/global.css` — resets, base styles
- `/styles/components.css` — reusable component classes
- `/pages/*.html` — individual pages

---

## 4. Asset Management

| Asset Type | Location | Notes |
|---|---|---|
| Images | Inline or `/assets/` directory | Use WebP with fallbacks |
| Icons | Inline SVG in HTML | Keeps HTTP requests minimal |
| Fonts | Google Fonts CDN (`preconnect`) | Inter, Instrument Serif, Manrope |
| Video | Removed — replaced with CSS animated gradient orbs | No external video dependencies |

### Asset guidelines
- Prefer inline SVG for icons (< 2KB each)
- Images should be optimized to WebP, max 200KB for hero images
- Use `loading="lazy"` on below-fold images
- All external resources must use `preconnect`

---

## 5. Icon System

Icons are **inline SVGs** embedded directly in the HTML markup.

```html
<!-- Navigation chevron example -->
<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
  <path d="M6 9L12 15L18 9" stroke="currentColor" stroke-width="2"
        stroke-linecap="round" stroke-linejoin="round"/>
</svg>
```

### Conventions
- Use `currentColor` for stroke/fill so icons inherit text color
- Standard viewBox: `0 0 24 24`
- Stroke-width: `1.5` or `2`
- Keep SVGs minimal — no unnecessary groups or metadata

---

## 6. Styling Approach

### Methodology
- **CSS Custom Properties** for all design tokens
- **BEM-influenced** class naming (section-element pattern)
- **No utility-first framework** — hand-written CSS for precision control
- Global styles live in a single `<style>` block in `<head>`

### Responsive Strategy

| Breakpoint | Target |
|---|---|
| Default | Desktop-first (1280px max-width container) |
| `max-width: 1024px` | Tablet |
| `max-width: 768px` | Mobile |

```css
/* Mobile adjustments */
@media (max-width: 768px) {
  .navbar { padding: 16px 20px; }
  .nav-links { display: none; }        /* hamburger menu TBD */
  .hero-center { padding: 100px 20px 0; }
  .hero-ctas { flex-direction: column; width: 100%; }
}
```

### Animation Conventions
- **Entrance:** `fade-in-up` (24px translate, 0.8s ease)
- **Hover:** `transform: translateY(-2px)` + glow shadow
- **Transitions:** `all 0.25s ease` for interactive elements
- **Background orbs:** Slow floating keyframes (14-20s cycle)
- **Pulsing indicators:** 2s ease-in-out infinite

---

## 7. Project Structure

```
MahaMaya/
  index.html          # Full site — markup, styles, content
  .gitignore          # Git ignore rules
  CLAUDE.md           # This file — design system rules
```

### Page Sections (index.html)

| Section | Purpose |
|---|---|
| Hero | Animated gradient bg, nav, headline, CTAs, dashboard preview |
| Services | Two-track offering (Local Services + E-Commerce) |
| Pricing | Tiered pricing cards for Track A and Track B |
| Social Proof | Testimonials, client logos, metrics |
| CTA / Footer | Final call-to-action, contact info, legal links |

---

## 8. Figma-to-Code Integration Rules

When translating Figma designs into this codebase:

1. **Map Figma tokens to CSS variables** — never use raw hex values; always reference `var(--token-name)`
2. **Maintain the dark-first aesthetic** — all backgrounds default to `--surface-primary` or `--surface-elevated`
3. **Typography must use the 3-font system** — Inter for headlines, Instrument Serif for italic accents, Manrope for everything else
4. **Glassmorphism cards** use `backdrop-filter: blur(16px)` with `var(--surface-subtle)` background and `var(--border-default)` border
5. **Interactive elements** always get hover states with `translateY(-2px)` and appropriate glow
6. **Spacing should snap to the scale** — use `var(--space-*)` tokens, not arbitrary pixel values
7. **New sections** follow the pattern: `<section class="[name]-section">` with a max-width container inside
8. **Responsive:** Desktop-first, single mobile breakpoint at 768px minimum. Use `clamp()` for fluid typography.
9. **No JavaScript frameworks** — keep everything in vanilla HTML/CSS. JS only for interactivity (scroll, modals, etc.)
10. **Gradient text** is achieved with `background-clip: text` + `-webkit-text-fill-color: transparent`, not color properties

---

## 9. Brand Voice in UI Copy

- **Authoritative, not aggressive.** "We build infrastructure" not "We crush the competition."
- **Technical precision.** Use terms like "Growth Systems," "Digital Infrastructure," "Commerce Engine."
- **Premium restraint.** Short sentences. No exclamation marks. Let the design speak.
- **Headlines:** Bold, declarative. Max 6 words per line.
- **Body copy:** 18px, relaxed line-height, muted color (`--text-secondary`).
