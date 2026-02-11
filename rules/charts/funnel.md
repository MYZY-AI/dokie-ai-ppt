# Funnel Chart

> Conversion funnels, filtering mechanisms, stage-wise reduction display

## Use Cases

- Marketing funnel (Visit → Sign up → Pay)
- Recruitment process (Resume → Interview → Hire)
- Sales pipeline (Lead → Opportunity → Close)
- Any filtering process from many to few

---

## Style Options

| Style | Characteristics | Use Case |
|-------|----------------|----------|
| **Smooth trapezoid** (recommended) | Straight edges, emphasizes flow | Most scenarios |
| **Stepped** | Layered blocks, emphasizes stage thresholds | Highlighting each stage's filtering |

---

## Technical Approach

**HTML + CSS (Flex + Clip-path)**

### Smooth Trapezoid Example

```html
<div class="funnel-container" style="
  width: 500px;
  aspect-ratio: 1.4;
  clip-path: polygon(0% 0%, 100% 0%, 70% 100%, 30% 100%);
  display: flex;
  flex-direction: column;
">
  <div class="stage" style="
    flex: 1;
    background: #theme-color-1;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    border-bottom: 2px solid white;
  ">
    <span>Visits 10,000</span>
  </div>

  <div class="stage" style="
    flex: 1;
    background: #theme-color-2;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    border-bottom: 2px solid white;
  ">
    <span>Sign-ups 3,000</span>
  </div>

  <div class="stage" style="
    flex: 1;
    background: #theme-color-3;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    border-bottom: 2px solid white;
  ">
    <span>Trials 800</span>
  </div>

  <div class="stage" style="
    flex: 1;
    background: #theme-color-4;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
  ">
    <span>Paid 200</span>
  </div>
</div>
```

---

## Layout Guidelines

### Key Rules

| Guideline | Description |
|-----------|-------------|
| **Parent container clip-path** | Apply funnel shape on parent container |
| **Flat bottom design** | `polygon(0% 0%, 100% 0%, 70% 100%, 30% 100%)` |
| **No pointed bottom** | Keep ~40% width to ensure bottom layer text is centered |
| **Aspect ratio** | Base `aspect-ratio: 1.2 ~ 1.6` (wider than pyramid) |
| **Text centering** | `justify-content: center` + `gap`, avoid `space-between` |

### Layer Count Recommendations

**Optimal: 3–5 layers**

### Bottom Text Handling

Ensure the bottom is wide enough for centered text:

```css
/* Bottom maintains 40% width */
clip-path: polygon(0% 0%, 100% 0%, 70% 100%, 30% 100%);
```

---

## Differences from Pyramid

| Comparison | Pyramid | Funnel |
|------------|---------|--------|
| Direction | Narrow top, wide bottom | Wide top, narrow bottom |
| clip-path | `polygon(50% 0%, 100% 100%, 0% 100%)` | `polygon(0% 0%, 100% 0%, 70% 100%, 30% 100%)` |
| Aspect ratio | 1.4–1.8 | 1.2–1.6 |
| Semantics | Hierarchy / importance | Process / conversion |

---

## Common Issues

### Wrong Approach

```css
/* Bottom too pointed, text gets clipped */
clip-path: polygon(0% 0%, 100% 0%, 50% 100%);

/* space-between pushes text to edges */
justify-content: space-between;
```

### Correct Approach

```css
/* Bottom maintains width */
clip-path: polygon(0% 0%, 100% 0%, 70% 100%, 30% 100%);

/* Text centered */
justify-content: center;
```

---

## Data Display Recommendations

Each layer should show:
- Stage name
- Count / percentage
- Optional: conversion rate

```html
<div class="stage">
  <span class="name">Sign-ups</span>
  <span class="value">3,000</span>
  <span class="rate">30%</span>
</div>
```
