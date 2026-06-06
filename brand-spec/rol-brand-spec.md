---
title: "Roll On Lunch — Colour Palette & Typography Spec"
version: "1.0"
date: "2026-06-06"
status: "Approved"
type: markdown
---

# Roll On Lunch — Colour Palette & Typography Spec

> **Status:** Approved v1.0 · June 2026  
> **Palette approved by:** Yorick Brown  
> **Accessibility:** All WCAG 2.1 AA compliant (full audit 2026-06-06)

---

## 1. Colour Palette

### Primary Colours

| Name | Hex | Role | WCAG vs Deep Leaf |
|------|-----|------|-------------------|
| **Tangerine** | `#FF8C38` | Primary energy — hero CTAs, pill backgrounds, highlight strokes | 5.83:1 AA ✓ |
| **Herb Garden** | `#3DAA6E` | Fresh / secondary — section accents, secondary buttons, success states | 4.62:1 AA ✓ |
| **Lime Zest** | `#B8E04A` | Playful accent — icons, tags, hover states, small pops | 8.88:1 AAA ✓ |

### Foundation Colours

| Name | Hex | Role |
|------|-----|------|
| **Deep Leaf** | `#1C3328` | Primary text colour, wordmark, all body copy |
| **Warm Parchment** | `#F5F0E8` | Page background, card base — warm white with personality |

### Soft Fill Colours

| Name | Hex | Role |
|------|-----|------|
| **Peach Blush** | `#FFE0CC` | Alert backgrounds, callout tints — never use with Tangerine text |
| **Pale Herb** | `#E8F5DC` | Hero tints, card hover states — Deep Leaf text only |

---

## 2. Contrast Compliance (WCAG 2.1)

### ✓ Approved Pairings

| Foreground | Background | Ratio | Level |
|-----------|------------|-------|-------|
| Deep Leaf `#1C3328` | Warm Parchment `#F5F0E8` | 10.81:1 | AAA |
| Deep Leaf `#1C3328` | Lime Zest `#B8E04A` | 8.88:1 | AAA |
| Deep Leaf `#1C3328` | Peach Blush `#FFE0CC` | 8.34:1 | AAA |
| Deep Leaf `#1C3328` | Pale Herb `#E8F5DC` | 9.12:1 | AAA |
| Deep Leaf `#1C3328` | Tangerine `#FF8C38` | 5.83:1 | AA |
| Deep Leaf `#1C3328` | Herb Garden `#3DAA6E` | 4.62:1 | AA |
| Warm Parchment `#F5F0E8` | Deep Leaf `#1C3328` | 10.81:1 | AAA |

### ⚠ Never Use Together

| Foreground | Background | Ratio | Reason |
|-----------|------------|-------|--------|
| White `#FFFFFF` | Tangerine `#FF8C38` | 2.32:1 | Fails AA — poor on CTAs |
| Lime Zest `#B8E04A` | Tangerine `#FF8C38` | 1.52:1 | Near-zero contrast |
| Tangerine `#FF8C38` | Peach Blush `#FFE0CC` | 1.85:1 | Fails AA |
| White `#FFFFFF` | Herb Garden `#3DAA6E` | 2.93:1 | Fails AA |

---

## 3. Typography System

### Font Stack

| Font | Weight | Role | Google Fonts |
|------|--------|------|-------------|
| **Playfair Display** | Bold 700 | Display, H1, H2, wordmark | [fonts.google.com/specimen/Playfair+Display](https://fonts.google.com/specimen/Playfair+Display) |
| **DM Sans** | 400 Regular, 500 Medium, 600 Semibold | Body, UI, H3–H6, buttons | [fonts.google.com/specimen/DM+Sans](https://fonts.google.com/specimen/DM+Sans) |
| **Libre Baskerville** | 400 Italic | Pull quotes, testimonials, bylines | [fonts.google.com/specimen/Libre+Baskerville](https://fonts.google.com/specimen/Libre+Baskerville) |

### Rationale

**Playfair Display Bold** — chosen for its editorial confidence and British broadsheet character. Playfair has the authority of a print magazine but sits comfortably on screen. The high contrast between thick and thin strokes gives ROL its premium-but-playful tone. Tracked at `+0.02em` for all display use to open it up.

**DM Sans** — geometric and modern without being sterile. Excellent legibility at small sizes on mobile, which is where most of our lunch-break readers are. The slightly rounded terminals keep it warm rather than clinical. Used at multiple weights to build a clear visual hierarchy.

**Libre Baskerville Italic** — the personality accent. Italicised serif in pull quotes slows the reader down in exactly the right way. It signals "this matters — read this bit." Lean on it for food descriptions, user reviews, and any line that deserves a moment.

### Type Scale

```
Display:   Playfair Display Bold  72–96px  tracking +0.02em
H1:        Playfair Display Bold  48–60px  tracking +0.02em
H2:        Playfair Display Bold  36–42px  tracking +0.01em
H3:        DM Sans Semibold       28–32px  tracking 0
H4:        DM Sans Semibold       22–24px  tracking 0
H5:        DM Sans Medium         18–20px  tracking 0
Body:      DM Sans Regular        16–18px  line-height 1.6
Small:     DM Sans Regular        14px     line-height 1.5
Micro:     DM Sans Regular        12px     caps + tracking +0.05em
Pull quote: Libre Baskerville Italic  24–28px  line-height 1.5
Byline:    DM Sans Medium Italic   16px
```

---

## 4. Colour × Type Pairing Guide

| Context | Background | Text Colour | Headline Font | Body Font |
|---------|-----------|------------|--------------|----------|
| Hero / Landing page | Deep Leaf | Warm Parchment | Playfair Display Bold 72–96px | DM Sans 18px |
| Article header | Deep Leaf | Warm Parchment | Playfair Display Bold 48–60px | DM Sans 20px |
| Section heading | Tangerine | Deep Leaf | DM Sans Semibold 28–32px | DM Sans 16px |
| CTA button | Tangerine | Deep Leaf | DM Sans Semibold 16–18px | — |
| Pull quote / callout | Peach Blush | Deep Leaf | Libre Baskerville Italic 24–28px | — |
| Tag / label chip | Lime Zest | Deep Leaf | DM Sans Medium 12–14px | — |
| Footer / legal / meta | Deep Leaf | Warm Parchment | DM Sans Regular 14px | — |

---

## 5. CSS Custom Properties

```css
:root {
  /* Colours */
  --col-tangerine:    #FF8C38;
  --col-herb-garden:  #3DAA6E;
  --col-lime-zest:    #B8E04A;
  --col-deep-leaf:    #1C3328;
  --col-warm-parchment: #F5F0E8;
  --col-peach-blush:  #FFE0CC;
  --col-pale-herb:    #E8F5DC;

  /* Typography */
  --font-display: 'Playfair Display', Georgia, serif;
  --font-body:    'DM Sans', system-ui, sans-serif;
  --font-accent:  'Libre Baskerville', Baskerville, Georgia, serif;

  /* Type scale */
  --text-display: clamp(3.5rem, 6vw, 6rem);
  --text-h1:      clamp(2.5rem, 4vw, 3.75rem);
  --text-h2:      clamp(1.8rem, 3vw, 2.625rem);
  --text-h3:      clamp(1.5rem, 2.5vw, 2rem);
  --text-body:    clamp(1rem, 1.5vw, 1.125rem);
  --text-small:   0.875rem;
  --text-micro:   0.75rem;

  /* Leading */
  --leading-tight:  1.2;
  --leading-snug:   1.4;
  --leading-normal: 1.6;
  --leading-loose:  1.8;

  /* Tracking */
  --tracking-display: 0.02em;
  --tracking-tight:   -0.01em;
  --tracking-normal:  0;
  --tracking-wide:    0.05em;
}
```

---

## 6. Figma / Canva Colour Tokens

```
Tangerine:      R=255 G=140 B=56   HEX #FF8C38
Herb Garden:    R=61  G=170 B=110  HEX #3DAA6E
Lime Zest:      R=184 G=224 B=74   HEX #B8E04A
Deep Leaf:      R=28  G=51  B=40   HEX #1C3328
Warm Parchment: R=245 G=240 B=232  HEX #F5F0E8
Peach Blush:    R=255 G=224 B=204  HEX #FFE0CC
Pale Herb:      R=232 G=245 B=220  HEX #E8F5DC
```

---

## 7. What This Means for the Website

- **Background:** Warm Parchment everywhere. Not white — the slight warmth makes food photography pop.
- **Text:** Deep Leaf, always. Never pure black.
- **Links:** Herb Garden on hover, Tangerine active/focus ring.
- **Buttons:** Tangerine fill, Deep Leaf text — the LUNCH pill is the CTA model.
- **Dark sections:** Deep Leaf background, Warm Parchment headlines, Lime Zest or Herb Garden accents.

---

*Roll On Lunch — Fresh · Playful · Alive*
