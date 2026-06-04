# Master Prompt — Hero Section UNIREB
## Para usar directo en Claude (con video adjunto)

---

Design a **hero section** for the official website of **UNIREB** (Universidad Rebsamen), a private university located in the Historic Center of Guadalajara, Mexico.

---

## Brand Identity

**Full name:** Centro Profesional Universitario Rébsamen Egloff A.C.
**Short name:** UNIREB
**Tagline:** "Actualidad en Educación con una Nueva Visión"

**Brand colors (extract exactly from the provided logo image):**
- Primary navy: `#0D2B6E`
- Mid blue: `#1A4BAD`
- Bright cyan / electric blue: `#2EB8E6`
- Accent highlight: `#3ABAFF`
- White: `#FFFFFF`

**Typography:**
- Headlines: bold, geometric sans-serif, uppercase, tightly tracked — similar to Barlow Condensed Bold or Bebas Neue
- Body/UI: clean modern sans-serif — Inter or DM Sans
- No serif fonts

**Logo:** Use the UNIREB logomark (the concentric arc symbol + UNIREB wordmark) in white version over dark backgrounds. Maintain clear space around it. Do not distort proportions.

---

## Hero Layout

**Stack:** Single-page HTML + CSS. Mobile-first. No frameworks, no dependencies.

**Structure (top to bottom):**

### 1. Sticky Navigation Bar
- Left: UNIREB logo (white, small — 36px tall max)
- Right: two text links ("Carreras" and "Inscripción") + one primary CTA button ("Inscríbete ya")
- CTA button: white background, navy text, pill shape, bold
- Background: semi-transparent navy `rgba(13,43,110,0.92)` with `backdrop-filter: blur(12px)`
- On mobile: hide text links, keep logo + CTA button only

### 2. Hero (full-viewport, 100svh)

**Background:** The provided video plays as a full-bleed autoplay loop (muted, no controls). Over it, apply a dark overlay gradient:
- `linear-gradient(to right, rgba(13,43,110,0.88) 0%, rgba(13,43,110,0.55) 60%, rgba(13,43,110,0.0) 100%)` on desktop
- `linear-gradient(to bottom, rgba(13,43,110,0.75) 0%, rgba(13,43,110,0.95) 100%)` on mobile

**Content (left-aligned on desktop, center on mobile):**

1. Small overline label:
   - Text: "GUADALAJARA · JALISCO · MÉXICO"
   - Style: all caps, letter-spacing 0.2em, 11px, electric cyan `#3ABAFF`, with a 2px cyan line to its left on desktop

2. Main headline (h1):
   - Line 1: "Prepárate para" — white, 56px desktop / 38px mobile, Barlow Condensed Bold
   - Line 2: "tu futuro." — electric cyan `#3ABAFF`, same size, creates color contrast

3. Subheadline:
   - Text: "Licenciaturas, diplomados y más. Turnos matutino, vespertino, nocturno y sabatino. Centro Histórico de Guadalajara."
   - Style: white 70% opacity, 16px, DM Sans Regular, max-width 480px

4. Stats row (3 items inline):
   - "15+" / "Carreras disponibles"
   - "4" / "Turnos flexibles"
   - "Av. SEP" / "Incorporado"
   - Each stat: number in bold cyan, label in small white/muted text below
   - Separated by a 1px white/20% vertical divider

5. CTA buttons (two):
   - Primary: "Inscríbete ahora" — solid cyan `#2EB8E6`, white text, bold, pill shape, 52px height
   - Secondary: "Ver carreras" — transparent background, white border 1.5px, white text, same size
   - Gap: 12px between them
   - On mobile: stack vertically, full width

6. Bottom trust bar (pinned to hero bottom, full width):
   - Background: `rgba(255,255,255,0.06)` with top border `rgba(255,255,255,0.1)`
   - Text: "Incorporada a la SEP · ESDIP-2019-16 · +33 12 00 29 87 · vinculacionrebsamen@outlook.com"
   - Style: 12px, white 60% opacity, centered, letter-spacing 0.05em

---

## Technical Requirements

- `<video autoplay muted loop playsinline>` — the video source should be a placeholder path `/video/hero.mp4` so it can be swapped
- `object-fit: cover` on the video, absolutely positioned behind all content
- Use `100svh` for hero height to avoid mobile browser chrome issues
- All text must meet WCAG AA contrast (4.5:1) against the overlaid video background
- Animate in the content on load: headline fades up (translateY 24px → 0, opacity 0 → 1, 600ms ease-out), subheadline and CTAs follow with 120ms stagger
- Respect `prefers-reduced-motion`: if set, skip animations entirely
- No horizontal scroll at any viewport
- Touch targets minimum 44×44px
- Font imports via Google Fonts: Barlow Condensed (700) + Inter (400, 500, 600)

---

## Mood & Reference

- Premium private university, accessible price point but aspirational feel
- Dark cinematic — feels like a modern institution, not a cheap local school
- Inspired by: UDLAP, Tec de Monterrey microsites, modern SaaS hero sections
- NOT: flat government sites, clip-art heavy, over-decorated
- The video background should feel like the hero breathes and lives — the overlay ensures readability at all times

---

## Deliverable

Single `.html` file with all CSS embedded in `<style>` tag. No external dependencies except Google Fonts. The video tag references `/video/hero.mp4` as placeholder. Code must be clean, commented by section, and production-ready.
