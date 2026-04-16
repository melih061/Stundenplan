# Synotix Design System — AI Reference v1.0
# Industrial Orange · Dark-First · Mittelstand B2B

## OVERVIEW
This is the complete design token reference for all Synotix frontends.
The style is: dark industrial background, single orange accent, zero border-radius.
Do NOT deviate from these tokens. Do NOT add a second accent color.

---

## DESIGN PHILOSOPHY
- Industrial, technical, precise — not playful or friendly
- Dashboard-first: UI looks like a real monitoring tool
- One accent color only: orange — all other colors are neutrals
- Zero border-radius on all panels, buttons, cards, inputs
- Mono font for all labels, nav links, tags, code, technical text
- Blueprint grid patterns for dark section backgrounds
- No purple, no gradient backgrounds, no rounded corners

---

## COLOR TOKENS (CSS Custom Properties)

```css
/* ── DARK BACKGROUNDS (standard mode) ── */
--bg-0:  #131311;   /* deepest surface — hero-right, modal backdrops */
--bg-1:  #1A1A17;   /* page base background */
--bg-2:  #212120;   /* panel / card surface */
--bg-3:  #2C2C29;   /* elevated panel / hover state */
--bg-4:  #363633;   /* highest elevation / tooltip */

/* ── LIGHT BACKGROUNDS (light variant) ── */
--lt-0:  #F4F2ED;   /* warm off-white — page base in light mode */
--lt-1:  #ECEAE4;   /* panel surface in light mode */
--lt-2:  #E2DFD8;   /* panel hover in light mode */
--lt-3:  #D6D3CB;   /* deepest light tone */

/* ── DARK-GREY STRUCTURE (nav/footer/dark sections in light variant) ── */
--dk-0:  #26251F;   /* nav & footer background */
--dk-1:  #302E28;   /* dark section base */
--dk-2:  #3C3A33;   /* dark section panel */
--dk-3:  #4A4840;   /* dark section hover */

/* ── THE ONLY ACCENT ── */
--orange:      #FF8C3F;   /* PRIMARY ACCENT — CTAs, borders-on-hover, active states, icons, eyebrows */
--orange-dim:  #E0721F;   /* Hover/pressed state of orange elements */
--orange-glow: #FF8C3F33; /* Soft glow backgrounds, focus rings */
--orange-line: #FF8C3F55; /* Subtle decorative borders, dividers */

/* ── TEXT ON DARK SURFACES ── */
--tx-d0: #F0EDE8;   /* primary text on dark */
--tx-d1: #A8A49E;   /* secondary text on dark */
--tx-d2: #6A6660;   /* muted/metadata text on dark */

/* ── TEXT ON LIGHT SURFACES ── */
--tx-l0: #1A1816;   /* primary text on light */
--tx-l1: #5A5650;   /* secondary text on light */
--tx-l2: #8A8680;   /* muted/metadata text on light */

/* ── BORDERS ── */
--bd:    rgba(255,255,255,0.08);  /* subtle border on dark */
--bd-hi: rgba(255,255,255,0.14); /* visible border on dark */
--bl:    rgba(26,24,22,0.10);    /* subtle border on light */
--bl-hi: rgba(26,24,22,0.18);   /* visible border on light */

/* ── GRID LINES ── */
--gd:    rgba(255,255,255,0.04); /* blueprint grid on dark */
--gl:    rgba(26,24,22,0.05);   /* blueprint grid on light */

/* ── LOGO AMBER (ONLY for the chevron logo mark — NOT as UI accent) ── */
--gold-a: #F5AC58;   /* top of gradient — warm amber */
--gold-b: #D07428;   /* mid of gradient — orange-copper */
--gold-c: #8A4410;   /* bottom of gradient — deep rust */

/* ── STATUS COLORS (only for data status indicators, never for design) ── */
--ok:   #22C55E;     /* success / active */
--warn: var(--orange); /* warning (reuses accent) */
--info: #60A5FA;     /* informational */
```

---

## TYPOGRAPHY

### Font Families
```
Display:  'Lora', serif              → weight 500 only (italic accents allowed)
Body:     'Space Grotesk', sans-serif → weights 400/500
Mono:     'JetBrains Mono', monospace → weights 400/500
```

### Google Fonts Import
```html
<link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,500;1,500&family=Space+Grotesk:wght@400;500&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
```

### CSS Font Variables
```css
--f-display: 'Lora', serif;               /* Headlines: 500 */
--f-body:    'Space Grotesk', sans-serif;  /* Body/Labels: 400/500 */
--f-mono:    'JetBrains Mono', monospace;  /* Tags, Code: 400/500 */
```

### Type Scale
| Class     | Font         | Weight | Size                        | Usage                    |
|-----------|--------------|--------|-----------------------------|--------------------------|
| .t-hero   | Lora         | 500    | clamp(40px, 5vw, 68px)      | Hero H1                  |
| .t-h1     | Lora         | 500    | 48px / ls -0.01em           | Page title               |
| .t-h2     | Lora         | 500    | 36px / ls -0.01em           | Section heading          |
| .t-h3     | Lora         | 500    | 18px                        | Card/panel heading       |
| .t-body   | Space Grotesk| 400    | 15px / lh 1.65              | Body text                |
| .t-small  | Space Grotesk| 400    | 13px / lh 1.6               | Supporting text          |
| .t-label  | Mono         | 400    | 10px / ls 0.14em / uppercase| Section eyebrow labels   |
| .t-tag    | Mono         | 400    | 9px / ls 0.10em / uppercase | Tech tags, badges        |
| .t-nav    | Mono         | 400    | 11px / ls 0.12em / uppercase| Navigation links         |
| .t-code   | Mono         | 400    | 12px / ls 0.02em            | Code, CLI output         |

### Letter-spacing Rules
- Display headings: `-0.01em` (slightly tight)
- Body text: `normal` (no adjustment)
- Mono labels: `+0.10em` to `+0.20em` (airy, uppercase-optimized)
- Wordmark "SYNOTIX": `+0.32em`

---

## LOGO

### SVG Mark — Double Chevron (copy this exactly)
```html
<!-- Define once in <body>, reference anywhere -->
<svg style="position:absolute;width:0;height:0;overflow:hidden" aria-hidden="true">
  <defs>
    <linearGradient id="gLogo" x1="40" y1="0" x2="40" y2="86" gradientUnits="userSpaceOnUse">
      <stop offset="0%"   stop-color="#F5AC58"/>
      <stop offset="40%"  stop-color="#D07428"/>
      <stop offset="100%" stop-color="#8A4410"/>
    </linearGradient>
    <!-- Gradient mark (standard) -->
    <symbol id="syn-mark" viewBox="0 0 80 86">
      <polygon points="12,4 62,28 12,52 12,42 52,28 12,14" fill="url(#gLogo)"/>
      <polygon points="68,34 18,58 68,82 68,72 28,58 68,44" fill="url(#gLogo)"/>
    </symbol>
    <!-- White mono variant -->
    <symbol id="syn-mark-w" viewBox="0 0 80 86">
      <polygon points="12,4 62,28 12,52 12,42 52,28 12,14" fill="#F0EDE8"/>
      <polygon points="68,34 18,58 68,82 68,72 28,58 68,44" fill="#F0EDE8"/>
    </symbol>
    <!-- Dark mono variant (on light backgrounds) -->
    <symbol id="syn-mark-dk" viewBox="0 0 80 86">
      <polygon points="12,4 62,28 12,52 12,42 52,28 12,14" fill="#1A1816"/>
      <polygon points="68,34 18,58 68,82 68,72 28,58 68,44" fill="#1A1816"/>
    </symbol>
    <!-- Orange variant -->
    <symbol id="syn-mark-or" viewBox="0 0 80 86">
      <polygon points="12,4 62,28 12,52 12,42 52,28 12,14" fill="#FF8C3F"/>
      <polygon points="68,34 18,58 68,82 68,72 28,58 68,44" fill="#FF8C3F"/>
    </symbol>
  </defs>
</svg>

<!-- Usage by size -->
<svg width="13" height="14" viewBox="0 0 80 86"><use href="#syn-mark"/></svg>  <!-- XS: Footer -->
<svg width="17" height="18" viewBox="0 0 80 86"><use href="#syn-mark"/></svg>  <!-- SM: Sidebar -->
<svg width="24" height="26" viewBox="0 0 80 86"><use href="#syn-mark"/></svg>  <!-- MD: Nav -->
<svg width="36" height="39" viewBox="0 0 80 86"><use href="#syn-mark"/></svg>  <!-- LG: Section -->
<svg width="52" height="56" viewBox="0 0 80 86"><use href="#syn-mark"/></svg>  <!-- XL: Hero -->
```

### Logo Lockup (Mark + Separator + Wordmark)
```html
<div style="display:inline-flex;align-items:center">
  <svg width="24" height="26" viewBox="0 0 80 86"><use href="#syn-mark"/></svg>
  <!-- 1px vertical separator -->
  <div style="width:1px;height:26px;margin:0 18px;background:linear-gradient(180deg,transparent,#FF8C3F 30%,#FF8C3F 70%,transparent);opacity:0.75"></div>
  <span style="font-family:'Lora',serif;font-weight:500;font-size:28px;letter-spacing:0.32em;color:#FFFFFF;text-transform:uppercase">SYNOTIX</span>
</div>
```

### Logo Glow Animation
```css
@keyframes markGlow {
  0%, 100% { filter: drop-shadow(0 0 6px rgba(208,116,40,0.28)); }
  50%       { filter: drop-shadow(0 0 20px rgba(245,172,88,0.60)); }
}
.mark-glow { animation: markGlow 5s ease-in-out infinite; }
```

### Logo Color Rules
- Mark (default): Amber gradient `#F5AC58 → #D07428 → #8A4410`
- Mark (mono white): `#F0EDE8` — for small sizes on dark bg
- Mark (mono dark): `#1A1816` — for light backgrounds
- Mark (orange): `#FF8C3F` — accent variant
- Wordmark on dark: `#FFFFFF`
- Wordmark on light: `#1A1816`
- Amber gradient is ONLY for the logo mark — never use as UI accent color

---

## COMPONENTS

### Buttons
```css
/* All buttons: no border-radius, mono font, uppercase */
.btn-primary  { background: #FF8C3F; color: #fff; }
.btn-primary:hover { background: #E0721F; }

.btn-ghost-d  { border: 1px solid rgba(255,255,255,0.14); color: #F0EDE8; }
.btn-ghost-d:hover { border-color: #FF8C3F; color: #FF8C3F; }

.btn-ghost-l  { border: 1px solid rgba(26,24,22,0.18); color: #1A1816; }
.btn-ghost-l:hover { border-color: #FF8C3F; color: #FF8C3F; }
```

### Cards (Dark)
```css
.card-d {
  background: #212120;
  border: 1px solid rgba(255,255,255,0.08);
  padding: 24px;
}
.card-d:hover { border-color: #FF8C3F; }

/* Accent top-bar variant */
.card-d.accent::before {
  content: ''; display: block; height: 2px;
  margin: -24px -24px 20px;
  background: #FF8C3F;
}
```

### Cards (Light)
```css
.card-l {
  background: #ECEAE4;
  border: 1px solid rgba(26,24,22,0.10);
  padding: 24px;
}
.card-l:hover { border-color: #FF8C3F; background: #E2DFD8; }
```

### Tags & Badges
```css
/* Tech tag (dark surface) */
.tag {
  font-family: 'JetBrains Mono', monospace;
  font-size: 9px; letter-spacing: 0.10em; text-transform: uppercase;
  padding: 3px 8px;
  border: 1px solid rgba(255,255,255,0.08);
  color: #6A6660;
}
.tag-orange { border-color: #FF8C3F; color: #FF8C3F; }

/* Status badges */
.badge-ok   { background: rgba(34,197,94,0.12);  color: #22C55E; }
.badge-warn { background: rgba(255,140,63,0.12); color: #FF8C3F; }
.badge-info { background: rgba(96,165,250,0.12); color: #60A5FA; }
```

### Eyebrow Label
```html
<!-- Orange line + uppercase label above headings -->
<div class="eyebrow">Leistungen</div>
```
```css
.eyebrow {
  display: flex; align-items: center; gap: 12px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px; letter-spacing: 0.20em; text-transform: uppercase;
  color: #FF8C3F; margin-bottom: 16px;
}
.eyebrow::before {
  content: ''; width: 24px; height: 1px;
  background: #FF8C3F; display: block; flex-shrink: 0;
}
```

### Navigation (standard dark nav)
```css
nav {
  background: #131311;
  border-bottom: 1px solid #FF8C3F55;
  height: 60px;
  padding: 0 48px;
  display: flex; align-items: center; justify-content: space-between;
  position: sticky; top: 0; z-index: 100;
}
a.nav-link {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px; letter-spacing: 0.12em; text-transform: uppercase;
  color: #A8A49E; text-decoration: none;
  transition: color 0.2s;
}
a.nav-link:hover, a.nav-link.active { color: #FF8C3F; }
```

---

## BACKGROUND PATTERNS

### Blueprint Grid (dark sections)
```css
.bg-grid-dark {
  background-color: #131311;
  background-image:
    linear-gradient(rgba(255,255,255,0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,0.04) 1px, transparent 1px),
    linear-gradient(rgba(255,140,63,0.033) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,140,63,0.033) 1px, transparent 1px);
  background-size: 20px 20px, 20px 20px, 100px 100px, 100px 100px;
}
```

### Blueprint Grid (light sections)
```css
.bg-grid-light {
  background-color: #F4F2ED;
  background-image:
    linear-gradient(rgba(26,24,22,0.05) 1px, transparent 1px),
    linear-gradient(90deg, rgba(26,24,22,0.05) 1px, transparent 1px);
  background-size: 24px 24px;
}
```

### Ruler Strip (section divider)
```css
.ruler {
  height: 20px;
  background-image: repeating-linear-gradient(
    90deg, transparent, transparent 9px,
    rgba(255,140,63,0.25) 9px, rgba(255,140,63,0.25) 10px
  );
  border-top: 1px solid rgba(26,24,22,0.10);
  border-bottom: 1px solid rgba(26,24,22,0.10);
  position: relative; overflow: hidden;
}
.ruler::before {
  content: ''; position: absolute; inset: 0;
  background-image: repeating-linear-gradient(
    90deg, transparent, transparent 49px,
    rgba(255,140,63,0.55) 49px, rgba(255,140,63,0.55) 50px
  );
}
```

### Glow Line (bottom edge of hero sections)
```css
.glow-line {
  position: absolute; bottom: 0; left: 0; right: 0;
  height: 1px;
  background: linear-gradient(90deg, transparent, #FF8C3F, transparent);
  opacity: 0.55;
}
```

### Accent Bar Left (left edge of hero text column)
```css
.accent-bar-left {
  position: absolute; left: 0; top: 0; bottom: 0;
  width: 3px; background: #FF8C3F;
}
```

---

## LAYOUT PATTERNS

### Split Hero (50/50)
```css
.split-hero {
  display: grid;
  grid-template-columns: 1fr 1fr;
  min-height: 88vh;
}
/* Left: light background + text, Right: dark + blueprint grid + dashboard */
```

### 4-Column Metrics Strip
```css
.metrics-strip {
  display: grid; grid-template-columns: repeat(4, 1fr);
  background: #131311;
  border-top: 1px solid #FF8C3F55;
  border-bottom: 1px solid #FF8C3F55;
}
```

### 3-Column Card Grid
```css
.card-grid-3 { display: grid; grid-template-columns: repeat(3, 1fr); gap: 2px; }
```

### 4-Phase Process
```css
.process-4 { display: grid; grid-template-columns: repeat(4, 1fr); }
.process-4 .step {
  padding: 32px;
  border-right: 1px solid rgba(255,255,255,0.08);
  border-top: 2px solid transparent;
}
.process-4 .step.active { border-top-color: #FF8C3F; }
```

### Dashboard (Sidebar + Main)
```css
.dash-layout { display: grid; grid-template-columns: 260px 1fr; }
/* Sidebar: bg-0 dark, Main: bg-2 slightly lighter */
```

---

## ANIMATIONS

```css
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(24px); }
  to   { opacity: 1; transform: translateY(0); }
}

/* Staggered card reveal */
.stagger > *:nth-child(1) { animation: fadeUp 0.5s 0.05s ease both; }
.stagger > *:nth-child(2) { animation: fadeUp 0.5s 0.12s ease both; }
.stagger > *:nth-child(3) { animation: fadeUp 0.5s 0.19s ease both; }
.stagger > *:nth-child(4) { animation: fadeUp 0.5s 0.26s ease both; }
.stagger > *:nth-child(5) { animation: fadeUp 0.5s 0.33s ease both; }
.stagger > *:nth-child(6) { animation: fadeUp 0.5s 0.40s ease both; }

/* Live status indicator */
@keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0.3; } }
.live-dot {
  width: 6px; height: 6px; border-radius: 50%;
  background: #22C55E; box-shadow: 0 0 6px #22C55E;
  animation: blink 2s ease-in-out infinite;
}
```

---

## LIGHT/DARK MODE

### Activation
```html
<!-- Dark (default) -->
<html data-theme="dark">

<!-- Light -->
<html data-theme="light">
```

### Light Mode Variable Overrides
```css
html[data-theme="light"] {
  --bg-0:  #ECEAE4;
  --bg-1:  #F4F2ED;
  --bg-2:  #ECEAE4;
  --bg-3:  #E2DFD8;
  --bg-4:  #D6D3CB;
  --tx-d0: #1A1816;
  --tx-d1: #2E2C28;   /* darker than dark-mode default for contrast on cream */
  --tx-d2: #4A4742;   /* darker than dark-mode default for contrast on cream */
  --bd:    rgba(26,24,22,0.10);
  --bd-hi: rgba(26,24,22,0.18);
  --gd:    rgba(26,24,22,0.05);
  --orange-glow: #FF8C3F22;
  --orange-line: #FF8C3F44;
}
/* Nav/footer always stay dark even in light mode */
html[data-theme="light"] nav { background: #26251F; }
```

---

## STRICT RULES — WHAT IS FORBIDDEN

```
✗  border-radius > 2px on any panel, card, or button
✗  Second accent color (no teal, no blue, no purple as design color)
✗  Gradient backgrounds on surfaces (only on text and logo mark)
✗  [DB] [AI] [RAG] bracket-style placeholder icons — use numbers or real SVGs
✗  Inter / Roboto / Arial / system-ui fonts
✗  DM Sans / Syne (old font stack — replaced by Lora + Space Grotesk)
✗  Purple or blue as background or dominant color
✗  More than one glow effect per viewport
✗  Full-width orange backgrounds (orange is accent only, not surface)
✗  Using the amber logo gradient (#F5AC58–#8A4410) as a UI color
```

## STRICT RULES — WHAT IS REQUIRED

```
✓  border-radius: 0 everywhere
✓  Single accent: #FF8C3F only
✓  JetBrains Mono for all labels, tags, nav, badges, code
✓  Lora 500 for all display headings (serif intentional — not body/labels)
✓  Space Grotesk for body text and UI labels
✓  Blueprint grid on dark hero / dark section backgrounds
✓  Ruler strips as section dividers
✓  Section eyebrows with orange line + uppercase mono label
✓  Numbers (01, 02, 03) instead of bracket icons
✓  Status colors only for actual data status, not decoration
```

---

## REFERENCE FILES

| File | Purpose |
|------|---------|
| `synotix-style.html` | Interactive style guide — all tokens + components with light/dark toggle |
| `synotix-logo.html` | Logo system — all sizes, variants, contexts (chevron mark) |
| `frontseite-final.html` | Full frontend mockup (dark/light toggle) |
| `frontseite-kupfer.html` | Copper accent variant |
| `frontseite-chrom.html` | Chrome/silver variant |

---

*Aktualisiert: 2026-04 · Synotix Design System Industrial Orange v1.0*
