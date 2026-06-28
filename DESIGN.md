<!-- SEED: re-run /impeccable document once there's code to capture the actual tokens and components. -->

---
name: Logistik Demo
description: A logistics marketplace demo that converts prospects through precision, not persuasion.
---

# Design System: Logistik Demo

## 1. Overview

**Creative North Star: "The Pre-Dawn Terminal"**

The moment before the world's cargo moves. A container port at 4am — dark water, cobalt sky breaking, amber dock lights cutting through mist. Machinery hums at exact tolerances. Nothing decorative. Everything load-bearing.

This system rejects the interchangeable SaaS aesthetic: white backgrounds, generic blue CTAs, and dashboards that claim capability rather than demonstrate it. It also refuses the old-school freight look — no highway imagery, no clip-art trucks, no Times New Roman. Instead it carries the energy of precision engineering: dark surfaces, one luminous cobalt brand color as a beacon, a warm amber accent that evokes instrumentation rather than celebration.

Typography is single-family, weighted for hierarchy. Motion is choreographed, not scattered — timed the way freight routing is timed: with purpose, no idle cycles. Every fold of the page has one job, and the design enforces it.

**Key Characteristics:**
- Dark surface, committed cobalt — the color does the brand's work, not the copy
- Barlow sans: condensed display weight, normal body weight — industrial precision without rigidity
- Amber accent for highlight and status — warm contrast that earns its moments
- Orchestrated entrance motion — quality-signal, never gratuitous
- One next action per fold — every section funnels, nothing dead-ends
- Data as protagonist — numbers, routes, metrics are the heroes; chrome recedes

## 2. Colors

A committed dark palette anchored by luminous cobalt — one saturated color carries 40–50% of the surface. Amber is the secondary voice, used sparingly for emphasis and instrumentation warmth.

### Primary
- **Beacon Cobalt** (`oklch(0.60 0.185 228)` — [to be resolved to hex during implementation]): The brand's defining color. Used for primary CTAs, active state indicators, key data callouts, and structural accents. Hue 228 reads as cold marine blue — distinct from generic SaaS violet-blue (hue ~265). On dark backgrounds it reads as luminous. White text on filled cobalt.

### Secondary
- **Dock Amber** (`oklch(0.82 0.120 75)` — [to be resolved during implementation]): Warm dock-light gold. Used for secondary badges, status indicators, hover accent rules, and highlight moments. Hue 75 (amber-gold) provides maximum hue contrast against cobalt. Dark text on amber fills.

### Neutral
- **Terminal Black** (`oklch(0.08 0.000 0)` — [to be resolved during implementation]): Pure near-black body background. No tint — the cobalt carries the brand, the surface is neutral.
- **Panel Surface** (`oklch(0.13 0.000 0)` — [to be resolved during implementation]): Card and panel surfaces — a single luminosity step above the background.
- **Near-White Ink** (`oklch(0.95 0.000 0)` — [to be resolved during implementation]): Primary body text. High contrast against the dark background, no tint.
- **Fog Gray** (`oklch(0.50 0.000 0)` — [to be resolved during implementation]): Secondary/muted text, metadata, supporting labels.

### Named Rules

**The Beacon Rule.** Cobalt appears on every screen, but only once as the dominant element — one primary CTA, one key metric highlighted. It earns its luminosity by scarcity. A screen full of cobalt is a screen full of noise.

**The Anti-Blue Rule.** Never use a blue with hue angle between 255–275 in OKLCH. That is the generic SaaS blue attractor zone (#2563EB, #3B82F6, Tailwind blue-500/600). The brand's cobalt lives at hue 228 — colder, more marine, more distinctive.

## 3. Typography

**Display / Headline Font:** Barlow Condensed (condensed weight variant for display, semi-bold for headlines)
**Body Font:** Barlow (regular and medium weights)
**Label Font:** Barlow (small, medium weight, uppercase tracking for metadata only)

**[Font pairing to be confirmed at implementation — verify Barlow Condensed and Barlow are loaded together; single-family system is the intent.]**

**Character:** A single-family system with committed weight contrast — the same typeface becomes a display instrument at 700-condensed and a readable body workhorse at 400-normal. The effect reads as engineering efficiency: one tool, used well, at multiple registers. Not two fonts pretending to be a system.

### Hierarchy

- **Display** (Barlow Condensed, 700, `clamp(3rem, 6vw, 6rem)`, line-height 0.95–1.00, letter-spacing -0.02em): Hero headings only. Condensed, bold, authoritative. `text-wrap: balance`.
- **Headline** (Barlow, 600, `clamp(1.75rem, 3.5vw, 2.75rem)`, line-height 1.1): Section leaders. Normal width, still confident. `text-wrap: balance`.
- **Title** (Barlow, 600, `clamp(1.125rem, 2vw, 1.375rem)`, line-height 1.25): Card headers, feature names, UI labels in context.
- **Body** (Barlow, 400, `1rem`/`1.0625rem`, line-height 1.65): Prose, descriptions, supporting copy. Max 65–70ch line length. `text-wrap: pretty`.
- **Label** (Barlow, 500, `0.6875rem`/`0.75rem`, letter-spacing 0.08–0.12em, uppercase): Metadata labels, status chips, navigation items, form field labels. Uppercase ONLY for this role — never for body or headline copy.

### Named Rules

**The Single-Family Rule.** Barlow at multiple widths and weights constitutes the entire type system. Do not introduce a second family as a "display serif for elegance" or "mono for tech signals" unless the brief specifically requires a mono sidecar (and this brief does not). Single-family fluency is harder and better.

**The Ceiling Rule.** Display headings are clamped at 6rem maximum. Above that the page shouts; below that it earns authority. Condensed type at large sizes reads as confident, not bulky — trust the weight.

## 4. Elevation

This is a dark-bg system. Elevation is expressed through **luminosity steps**, not shadows: each layer is a slightly lighter neutral, using the bg → surface → surface-raised progression. Shadows are prohibited as a depth signal on dark backgrounds — they flatten and muddy. The exception is glow: a cobalt or amber diffuse outer glow can be used on interactive focused elements (not cards, not static surfaces).

**The Luminosity Rule.** Higher = lighter. Background sits at L 0.08. Panels sit at L 0.13. Modals/sheets sit at L 0.17. Dropdowns and tooltips sit at L 0.20. No shadows between layers; contrast comes from luminosity alone. If the elevation hierarchy isn't readable without a shadow, the luminosity steps are too close together — increase the gap, don't add a shadow.

## 5. Components

*Seed mode: no implemented components yet. Synthesized from token direction as a starting scaffold.*

### Buttons
- **Shape:** Sharp or very subtly rounded — `border-radius: 4px` maximum. No soft pill shapes; no fully rounded capsule buttons. The system is precise, not friendly.
- **Primary:** Cobalt fill (`oklch(0.60 0.185 228)`), white text. Padding `14px 32px`. On hover: luminosity increase (`oklch(0.66 0.185 228)`), translate-y -1px, 150ms ease-out-quart.
- **Secondary / Ghost:** Transparent fill, cobalt 1px border, cobalt text. On hover: cobalt fill at 10% opacity.
- **Amber CTA (use sparingly):** Dock Amber fill, dark ink text. Reserved for the single most important conversion action per page.
- **States:** Focus-visible ring at 2px offset, cobalt color, no inset.

### Cards / Containers
- **Background:** Panel Surface (`oklch(0.13 0.000 0)`) — one luminosity step above body
- **Border:** 1px solid `oklch(0.20 0.000 0)` — subtle separation, no shadow
- **Corner Style:** `border-radius: 6px` — just enough to soften, not enough to soften the brand
- **Internal Padding:** `24px` desktop, `16px` mobile
- **Nested cards:** Forbidden. Elevation steps handle depth; nesting is visual noise.

### Navigation
- **Style:** Horizontal bar, body bg color, no shadow or bottom border. Site name at left in Barlow 600; nav links in Label style (uppercase, 0.10em tracking); CTA button at right.
- **Active state:** Cobalt underline rule (2px, full width of text), not background highlight.
- **Mobile:** Hamburger pattern; slide-in full-height overlay on Panel Surface bg.

### Inputs / Fields
- **Style:** Dark fill (`oklch(0.11 0.000 0)`), 1px border `oklch(0.22 0.000 0)`, `border-radius: 4px`, body text color.
- **Focus:** Border shifts to cobalt (1px → 1.5px); no box-shadow glow on inputs — only on buttons.
- **Placeholder:** Fog Gray (`oklch(0.50 0.000 0)`) — must clear 4.5:1 contrast minimum.
- **Error:** Amber border + amber label (not red — red is not in this palette).

## 6. Do's and Don'ts

### Do:
- **Do** use Beacon Cobalt (`oklch(0.60 0.185 228)`) as the singular brand signal — one dominant cobalt element per screen.
- **Do** use `clamp()` for all display and headline sizes to ensure fluid responsiveness without breakpoint hacks.
- **Do** keep luminosity steps distinct between bg, surface, and elevated surfaces — enough gap that the hierarchy reads without shadows.
- **Do** use white text on all cobalt fills and dark text on all amber fills.
- **Do** write `text-wrap: balance` on h1–h3 and `text-wrap: pretty` on body paragraphs.
- **Do** cap body line length at 65–70ch on prose sections.
- **Do** treat motion as a quality signal: choreographed entrance for hero sections, responsive feedback for interactions, reduced-motion fallbacks on every animation.
- **Do** restrict uppercase type to Label role only — headings and body copy are mixed-case.

### Don't:
- **Don't** use a blue with OKLCH hue between 255–275. That is the generic SaaS blue zone. The brand lives at hue 228.
- **Don't** use a white, cream, or near-white background. This system is dark. A cream background reads as the AI-design default and erases identity.
- **Don't** create data-dense, multi-column dashboard layouts. This is a marketing surface. One idea per fold, breathing room, clear hierarchy.
- **Don't** reference old-school freight or trucking visual language: no highway imagery, no clip-art trucks, no commodity-shipping aesthetics.
- **Don't** use gradient text (`background-clip: text` combined with a gradient). Solid color only.
- **Don't** use `border-left` wider than 1px as a decorative colored stripe on cards or callouts.
- **Don't** use glassmorphism for decorative purposes — blurred panels are not a brand element.
- **Don't** add an eyebrow label (`ABOUT`, `FEATURES`, `PRICING` in tiny tracked uppercase) above every section heading. If one section uses a kicker, it must be a deliberate system — not a reflexive scaffold repeated on every fold.
- **Don't** use numbered section markers (`01 / 02 / 03`) unless the content is a genuine sequential flow that requires order to be understood.
- **Don't** nest cards inside cards. If depth is needed, use a luminosity step, not a nested container.
