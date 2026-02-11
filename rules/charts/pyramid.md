# Pyramid Chart

> Hierarchical importance, need levels, capability models, organizational structure

## Use Cases

- Maslow's hierarchy of needs
- Capability / skill pyramid
- Organizational hierarchy
- Importance ranking (top = most important/fewest, bottom = foundation/most)

---

## Style Options

| Style | Characteristics | Use Case |
|-------|----------------|----------|
| **Smooth trapezoid** (recommended) | Straight edges, visually fluid, strong unity | Most scenarios |
| **Stepped** | Layered blocks, clear level separation | Emphasizing "foundation support" or "progressive improvement" |

---

## Technical Approach

**HTML + CSS (Flex + Clip-path)**

### Smooth Trapezoid Example

```html
<div class="pyramid-container" style="
  width: 400px;
  aspect-ratio: 1.5;
  clip-path: polygon(50% 0%, 100% 100%, 0% 100%);
  display: flex;
  flex-direction: column;
">
  <div class="layer" style="
    flex: 1;
    background: #theme-color-1;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    border-bottom: 2px solid white;
  ">Self-actualization</div>

  <div class="layer" style="
    flex: 1;
    background: #theme-color-2;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    border-bottom: 2px solid white;
  ">Esteem</div>

  <div class="layer" style="
    flex: 1;
    background: #theme-color-3;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    border-bottom: 2px solid white;
  ">Social needs</div>

  <div class="layer" style="
    flex: 1;
    background: #theme-color-4;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    border-bottom: 2px solid white;
  ">Safety needs</div>

  <div class="layer" style="
    flex: 1;
    background: #theme-color-5;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
  ">Physiological needs</div>
</div>
```

---

## Layout Guidelines

### Key Rules

| Guideline | Description |
|-----------|-------------|
| **Parent container clip-path** | Apply pyramid shape on parent container; child elements stay as stacked rectangles |
| **Do not clip per layer** | Causes alignment issues |
| **Aspect ratio** | Base `aspect-ratio: 1.4 ~ 1.8`, adjust based on content |
| **Spacing** | Smooth style uses `border-bottom`; stepped uses `margin-bottom` |
| **Text centering** | `display: flex; align-items: center; justify-content: center;` |

### Layer Count Recommendations

**Optimal: 3–5 layers**

Too many layers result in insufficient height per layer, making text display difficult.

### Top Layer Text Handling

If top layer text is long, adjust the clip-path formula to increase top width:

```css
/* Slightly flat top to ensure top layer text is centered */
clip-path: polygon(45% 0%, 55% 0%, 100% 100%, 0% 100%);
```

---

## Common Issues

### Wrong Approach

```html
<!-- Clipping each layer individually - causes misalignment -->
<div style="clip-path: ...">Layer 1</div>
<div style="clip-path: ...">Layer 2</div>
```

### Correct Approach

```html
<!-- Unified clip on parent container -->
<div class="pyramid" style="clip-path: polygon(50% 0%, 100% 100%, 0% 100%);">
  <div class="layer">Layer 1</div>
  <div class="layer">Layer 2</div>
</div>
```

---

## Color Recommendations

Extract gradient color palette from the theme:
- Top layer: Dark / accent color
- Bottom layer: Light / base color

Or reversed, depending on semantics.
