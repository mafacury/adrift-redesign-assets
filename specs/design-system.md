# Design System — Adrift Redesign

**Foundational tokens, typography, and component guidelines**

---

## 🎨 Color Palette

### Ocean Depths
| Token | Hex | RGB | Usage |
|-------|-----|-----|-------|
| `ocean-deep` | `#0D1B2E` | 13, 27, 46 | Dark backgrounds, water depths |
| `ocean-mid` | `#1B4F72` | 27, 79, 114 | Secondary water, accents |
| `ocean-surface` | `#2E86AB` | 46, 134, 171 | **Primary color**: buttons, active states |
| `ocean-light` | `#7EC8E3` | 126, 200, 227 | Highlights, shallow water |

### Sky & Atmosphere
| Token | Hex | RGB | Usage |
|-------|-----|-----|-------|
| `sky-blue` | `#87CEEB` | 135, 206, 235 | Daytime sky |
| `cloud-white` | `#F0F4F8` | 240, 244, 248 | Clouds, light cards |
| `sand` | `#D4A96A` | 212, 169, 106 | Warm wood, deck, sand |
| `gold-sun` | `#F5C518` | 245, 197, 24 | Sun, stars, achievements |

### Text & UI
| Token | Hex | RGB | Usage |
|-------|-----|-----|-------|
| `text-primary` | `#1A2840` | 26, 40, 64 | Titles on light backgrounds |
| `text-light` | `#FFFFFF` | 255, 255, 255 | Text over images/dark |
| `text-muted` | `#9CA3AF` | 156, 163, 175 | Secondary text, disabled |
| `paper` | `#F8F2E0` | 248, 242, 224 | Aged paper cards |
| `paper-border` | `#8B6F47` | 139, 111, 71 | Paper frame |
| `error` | `#E74C3C` | 231, 76, 60 | Errors, warnings |

### Semantic
| Token | Use Case |
|-------|----------|
| `success` | `#27AE60` – Positive actions |
| `warning` | `#F39C12` – Caution |
| `info` | `#3498DB` – Information |

---

## 📝 Typography

### Font Families

| Role | Font | Weights | Usage |
|------|------|---------|-------|
| **Display** | Cormorant Garamond | 400, 600 | Títulos de tela, marca, cartões |
| **Body/UI** | Inter | 400, 500, 600, 700 | Texto, botões, rótulos, menus |

### Type Scale

| Level | Font | Size | Weight | Line Height | Letter Spacing |
|-------|------|------|--------|------------|-----------------|
| **H1** | Cormorant | 54 px | 600 | 1.2 | −0.02em |
| **H2** | Cormorant | 36 px | 600 | 1.3 | −0.01em |
| **H3** | Cormorant | 28 px | 600 | 1.4 | 0 |
| **H4** | Cormorant | 21 px | 400 | 1.5 | 0 |
| **Body Large** | Inter | 16 px | 400 | 1.6 | 0 |
| **Body** | Inter | 15 px | 400 | 1.5 | 0 |
| **Body Small** | Inter | 13 px | 400 | 1.5 | 0 |
| **Label** | Inter | 12 px | 600 | 1.4 | 0.05em |
| **Caption** | Inter | 11 px | 400 | 1.4 | 0 |

---

## 🎯 Component Foundations

### Buttons

#### Primary Button (Pílula)
```css
Border Radius: 48 px (full pill)
Padding: 12 px 32 px (height ~48 px)
Background: ocean-surface (#2E86AB)
Text: text-light, Inter 600, 16 px
Border: none
Box Shadow: 0 4px 12px rgba(46, 134, 171, 0.3)
Hover: Background darkens 8%, shadow increases
Active: Scale 0.98
Disabled: Opacity 45%
```

#### Secondary Button
```css
Background: cloud-white (#F0F4F8)
Text: text-primary
Border: 1 px solid ocean-surface
Hover: Background lightens
```

#### Tertiary (Text Link)
```css
Background: transparent
Text: ocean-surface, underline on hover
```

### Cards

#### Glass Card (Translucent)
```css
Background: rgba(255, 255, 255, 0.88)
Backdrop Filter: blur(8px)
Border Radius: 16 px
Padding: 24 px
Box Shadow: 0 8px 32px rgba(0, 0, 0, 0.1)
Border: 1 px solid rgba(255, 255, 255, 0.2)
```

#### Paper Card (Aged)
```css
Background: paper (#F8F2E0)
Border: 3 px solid paper-border (#8B6F47)
Border Radius: 24 px
Padding: 20 px
Box Shadow: 0 8px 24px rgba(139, 111, 71, 0.15)
```

#### Mini Card (Message)
```css
Background: #FFFFFF
Border Radius: 14 px
Padding: 12 px 16 px
Box Shadow: 0 2px 8px rgba(0, 0, 0, 0.08)
Border: 1 px solid rgba(46, 134, 171, 0.1)
```

### Input Fields

```css
Background: #FFFFFF or rgba(255, 255, 255, 0.9)
Border: 2 px solid ocean-light (#7EC8E3)
Border Radius: 12 px
Padding: 12 px 16 px
Font: Inter 15 px, text-primary
Placeholder: text-muted
Focus: Border color ocean-surface, box-shadow 0 0 0 3px rgba(46, 134, 171, 0.1)
```

### Sidebar Navigation (Left, 80 px)

```css
Width: 80 px
Height: 100vh
Background: rgba(255, 255, 255, 0.96)
Backdrop Filter: blur(4px)
Border Right: 1 px solid rgba(0, 0, 0, 0.08)

Item:
- Icon: SVG 24 px, centered
- Label: Inter 10 px below icon
- Inactive: text-muted
- Active: text-ocean-surface, weight 600
- Padding: 16 px (top), 8 px (vertical spacing between items)
```

---

## 🎭 States & Interactions

### Hover
- Slight darkening (8–12% opacity reduction)
- Subtle shadow increase
- Cursor pointer

### Active / Selected
- Full color saturation
- Slightly brighter or more vivid tone
- Optional: thin highlight border

### Disabled
- Opacity: 45%
- Cursor: not-allowed
- No hover effect

### Loading
- Spinner: 24 px, ocean-surface color
- Text: "Consultando..." or "Salvando..."
- Button: disabled state while loading

### Error
- Background: error color with 8% opacity
- Border: error color, 1 px
- Text: error color, 13 px
- Icon: ⚠️ or ✕

---

## 📐 Spacing System

```
Base unit: 4 px

Scales:
- 4 px (xs)
- 8 px (sm)
- 12 px (md)
- 16 px (lg)
- 20 px (xl)
- 24 px (2xl)
- 32 px (3xl)
- 48 px (4xl)
```

### Padding & Margins
- Card padding: 20–24 px
- Button padding: 12 px vertical, 32 px horizontal
- Form spacing: 16 px between fields
- Section spacing: 32 px

---

## 🖼️ Background Images

### Resolution & Format
| Screen | Dimensions | Format | Quality | Max Size |
|--------|-----------|--------|---------|----------|
| Full screen (portrait) | 1080×1920 | JPG | 85% | < 100 KB |
| Mapa | 1280×628 | JPG | 85% | < 80 KB |

### CSS for Full-Screen BG
```css
background-image: url('path/to/image.jpg');
background-size: cover;
background-position: center;
background-attachment: fixed; /* Parallax on scroll */
```

---

## 🎬 Animations

### Transitions
```css
Button hover: all 200ms ease-out
State change: all 300ms ease-in-out
Opacity fade: 200ms linear
Transform (scale, translate): 300ms cubic-bezier(0.34, 1.56, 0.64, 1)
```

### Entrance
- Slide from left: 400ms ease-out, translateX(-40px → 0)
- Fade in: 300ms ease-out, opacity(0 → 1)
- Scale up: 300ms ease-out, scale(0.95 → 1)

### Exit
- Slide to right: 300ms ease-in, translateX(0 → 40px)
- Fade out: 200ms ease-in, opacity(1 → 0)

---

## 🔧 Implementation Notes

### CSS Variables (Optional, Recommended)
```css
:root {
  --color-ocean-surface: #2E86AB;
  --color-ocean-light: #7EC8E3;
  --color-text-light: #FFFFFF;
  --font-display: 'Cormorant Garamond', serif;
  --font-body: 'Inter', sans-serif;
  --radius-sm: 12px;
  --radius-md: 16px;
  --radius-lg: 24px;
  --radius-full: 48px;
  --shadow-sm: 0 2px 8px rgba(0, 0, 0, 0.08);
  --shadow-md: 0 4px 12px rgba(0, 0, 0, 0.12);
  --shadow-lg: 0 8px 32px rgba(0, 0, 0, 0.15);
}
```

### Responsive Breakpoints
```
Mobile: 320px – 767px (portrait first)
Tablet: 768px – 1024px
Desktop: 1025px+
```

---

**Last Updated:** Julho 2026  
**Version:** 1.0
