# RootRise by DEVONEERS — Color System v6.5 Final
## AI-&I Powered SME Transformation

*Designer: Ruba | Version: 6.5 Final | December 2025*

---

## The 4 Themes at a Glance

| Theme | Page BG | Card BG | Accent Primary | Title Color | Best For |
|-------|---------|---------|----------------|-------------|----------|
| **Light** | Cream #F5F1E8 | Gold Card #EDE0C8 | Teal #2A5C5C | Teal #2A5C5C | Forms, questionnaires, reports |
| **Teal** | Teal Dark #0D2626 | Teal Card #153838 | Gold #B8904A | Champagne #F7E7CE | Landing pages, hero sections |
| **Burgundy** | Teal Dark #0D2626 | Gold Card #EDE0C8 | Burgundy #722F37 | Gold #B8904A | Premium accents, high-contrast |
| **Gold** | Gold Card #EDE0C8 | Champagne #F7E7CE | Teal #2A5C5C | Teal #2A5C5C | Warm dashboards, balanced layouts |

---

## Base Colors (Shared Across All Themes)

### Gold Family
| Color Name | Hex Code | CSS Variable | Usage |
|------------|----------|--------------|-------|
| **Gold Primary** | `#B8904A` | `--gold-primary` | Brand color, CTAs, "Rise" in logo |
| Gold Card | `#EDE0C8` | `--gold-card` | Card backgrounds (Light/Burgundy/Gold) |
| Gold Card Hover | `#E5D5B8` | `--gold-card-hover` | Card hover states |
| Champagne | `#F7E7CE` | `--champagne` | Highlighted cards, selected states |

### Cream/Neutral Family
| Color Name | Hex Code | CSS Variable | Usage |
|------------|----------|--------------|-------|
| **Cream** | `#F5F1E8` | `--cream` | Page background (Light theme) |
| Cream Warm | `#F0EBE0` | `--cream-warm` | Subtle variation |
| Pearl | `#E8E0D0` | `--pearl` | Balance bar, subtle sections |
| Border Gold | `#C9B896` | `--border-primary` | Primary borders (Light/Gold) |
| Border Subtle | `#D4CFC4` | `--border-subtle` | Subtle dividers |

### Teal Family
| Color Name | Hex Code | CSS Variable | Usage |
|------------|----------|--------------|-------|
| **Teal** | `#2A5C5C` | `--teal` | Accent (Light/Gold), "Root" in logo |
| Teal Deep | `#1E4A4A` | `--teal-deep` | Card hover (Teal theme) |
| **Teal Dark BG** | `#0D2626` | `--teal-dark-bg` | Page background (Teal/Burgundy) |
| Teal Card Dark | `#153838` | `--teal-card-dark` | Card background (Teal theme) |

### Burgundy Family
| Color Name | Hex Code | CSS Variable | Usage |
|------------|----------|--------------|-------|
| **Burgundy** | `#722F37` | `--burgundy` | Accent primary (Burgundy theme) |
| Burgundy Tint | `#F5E8EA` | `--burgundy-tint` | Burgundy tag backgrounds |

### Text Colors
| Color Name | Hex Code | CSS Variable | Usage |
|------------|----------|--------------|-------|
| Text Dark | `#1A1A1A` | `--text-dark` | Primary text (Light/Gold) |
| Text Medium | `#4A4A4A` | `--text-medium` | Secondary text (Light/Gold) |
| Text Light | `#6A6A6A` | `--text-light` | Muted text (Light/Gold) |
| Text White | `#FFFFFF` | `--text-white` | Text on accent buttons |
| Text Cream | `#F5F1E8` | `--text-cream` | Primary text (Teal theme) |

---

## Theme 1: Light (Default)

**Use for:** Questionnaires, forms, reports, light reading content

```css
[data-theme="light"] {
    --bg-page: var(--cream);           /* #F5F1E8 */
    --bg-card: var(--gold-card);       /* #EDE0C8 */
    --bg-card-hover: var(--gold-card-hover); /* #E5D5B8 */
    --bg-hero: var(--cream);           /* #F5F1E8 */
    --border-primary: #C9B896;
    --border-subtle: #D4CFC4;
    --accent-primary: var(--teal);     /* #2A5C5C */
    --accent-secondary: var(--gold-primary); /* #B8904A */
    --text-primary: var(--text-dark);  /* #1A1A1A */
    --text-secondary: var(--text-medium); /* #4A4A4A */
    --text-muted: var(--text-light);   /* #6A6A6A */
    --text-on-accent: var(--text-white); /* #FFFFFF */
    --title-color: var(--teal);        /* #2A5C5C */
    --brand-color: var(--gold-primary); /* #B8904A */
}
```

---

## Theme 2: Teal (Dark)

**Use for:** Landing pages, hero sections, immersive brand moments

```css
[data-theme="teal"] {
    --bg-page: var(--teal-dark-bg);    /* #0D2626 */
    --bg-card: var(--teal-card-dark);  /* #153838 */
    --bg-card-hover: var(--teal-deep); /* #1E4A4A */
    --bg-hero: var(--teal-dark-bg);    /* #0D2626 */
    --border-primary: var(--teal);     /* #2A5C5C */
    --border-subtle: #1E4A4A;
    --accent-primary: var(--gold-primary); /* #B8904A */
    --accent-secondary: var(--champagne); /* #F7E7CE */
    --text-primary: var(--text-cream); /* #F5F1E8 */
    --text-secondary: #B8C4C4;
    --text-muted: #8A9E9E;
    --text-on-accent: var(--text-dark); /* #1A1A1A */
    --title-color: var(--champagne);   /* #F7E7CE */
    --brand-color: var(--gold-primary); /* #B8904A */
}
```

---

## Theme 3: Burgundy (Contrast)

**Use for:** Premium accents, special sections, high-contrast UI

```css
[data-theme="burgundy"] {
    --bg-page: var(--teal-dark-bg);    /* #0D2626 */
    --bg-card: var(--gold-card);       /* #EDE0C8 */
    --bg-card-hover: var(--gold-card-hover); /* #E5D5B8 */
    --bg-hero: var(--gold-card);       /* #EDE0C8 */
    --border-primary: var(--gold-primary); /* #B8904A */
    --border-subtle: var(--teal);      /* #2A5C5C */
    --accent-primary: var(--burgundy); /* #722F37 */
    --accent-secondary: var(--gold-primary); /* #B8904A */
    --text-primary: var(--champagne);  /* #F7E7CE */
    --text-secondary: #C4B8A8;
    --text-muted: #A89888;
    --text-on-accent: var(--text-white); /* #FFFFFF */
    --title-color: var(--gold-primary); /* #B8904A */
    --brand-color: var(--gold-primary); /* #B8904A */
}
```

---

## Theme 4: Gold (Warm)

**Use for:** Warm dashboards, balanced layouts, premium feel

```css
[data-theme="gold"] {
    --bg-page: var(--gold-card);       /* #EDE0C8 */
    --bg-card: var(--champagne);       /* #F7E7CE */
    --bg-card-hover: var(--cream);     /* #F5F1E8 */
    --bg-hero: var(--gold-card);       /* #EDE0C8 */
    --border-primary: var(--gold-primary); /* #B8904A */
    --border-subtle: #C9B896;
    --accent-primary: var(--teal);     /* #2A5C5C */
    --accent-secondary: var(--teal);   /* #2A5C5C */
    --text-primary: var(--text-dark);  /* #1A1A1A */
    --text-secondary: var(--text-medium); /* #4A4A4A */
    --text-muted: var(--text-light);   /* #6A6A6A */
    --text-on-accent: var(--text-white); /* #FFFFFF */
    --title-color: var(--teal);        /* #2A5C5C */
    --brand-color: var(--gold-primary); /* #B8904A */
}
```

---

## Semantic Variable Reference

| Variable | Purpose | Light | Teal | Burgundy | Gold |
|----------|---------|-------|------|----------|------|
| `--bg-page` | Page background | #F5F1E8 | #0D2626 | #0D2626 | #EDE0C8 |
| `--bg-card` | Card background | #EDE0C8 | #153838 | #EDE0C8 | #F7E7CE |
| `--bg-card-hover` | Card hover | #E5D5B8 | #1E4A4A | #E5D5B8 | #F5F1E8 |
| `--bg-hero` | Hero section | #F5F1E8 | #0D2626 | #EDE0C8 | #EDE0C8 |
| `--accent-primary` | Primary accent | #2A5C5C | #B8904A | #722F37 | #2A5C5C |
| `--accent-secondary` | Secondary accent | #B8904A | #F7E7CE | #B8904A | #2A5C5C |
| `--title-color` | Headings | #2A5C5C | #F7E7CE | #B8904A | #2A5C5C |
| `--brand-color` | Brand/logo | #B8904A | #B8904A | #B8904A | #B8904A |
| `--text-primary` | Main text | #1A1A1A | #F5F1E8 | #F7E7CE | #1A1A1A |
| `--text-on-accent` | Text on buttons | #FFFFFF | #1A1A1A | #FFFFFF | #FFFFFF |

---

## Logo Treatment

```
Root     Rise
#2A5C5C  #B8904A  (Light & Gold themes)
#F7E7CE  #B8904A  (Teal theme)
#B8904A  #B8904A  (Burgundy theme - all gold)
```

---

## Component Quick Reference

### Buttons
| Type | Background | Text | Border |
|------|------------|------|--------|
| Primary CTA | `--accent-primary` | `--text-on-accent` | None |
| Secondary CTA | Transparent | `--accent-primary` | `--accent-primary` |

### Badges
| Type | Background | Text |
|------|------------|------|
| CORE | `--accent-primary` | `--text-on-accent` |
| ADD-ON | Transparent | `--accent-secondary` (with border) |
| Theme Tag | Various per theme | Contrasting |

### Cards
| State | Background | Border |
|-------|------------|--------|
| Default | `--bg-card` | `--border-primary` |
| Hover | `--bg-card-hover` | `--border-primary` |
| Selected | `--champagne` | `--brand-color` |

---

## Balance Bar (Footer Element)

Visual representation of color distribution:
- **Beige (30%):** `--pearl` #E8E0D0
- **Gold (30%):** `--gold-primary` #B8904A
- **Teal (30%):** `--teal` #2A5C5C
- **Burgundy (10%):** `--burgundy` #722F37

---

## Implementation Notes

1. **Theme Switching:** Use `data-theme` attribute on `<html>` element
2. **Transitions:** Add `transition: background 0.4s ease, color 0.4s ease` for smooth switching
3. **Local Storage:** Save user preference with `localStorage.setItem('rootrise-theme', theme)`
4. **Default Theme:** Light is the default; load saved preference on page init

---

*Document extracted from RootRise v6.5 Final*
*For project knowledge integration — RootRise by DEVONEERS*
