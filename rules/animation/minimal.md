# Minimal Animation Style

> Static elegance, content is king. Let the content speak for itself.

## Use Cases

- Formal business reports
- Investor / client presentations
- Serious professional occasions
- When the content itself is the focus

---

## Animation Rules

### Cover / Ending Pages

| Allowed | Effects |
|---------|---------|
| Ambient background | Particles, Gradient Flow, Floating Shapes |
| Title entrance | Float Up, Fade In |

### Content Pages

| Rule | Description |
|------|-------------|
| **Only one page-level Fade** | Entire page fades in as a whole |
| **No element-level animations** | Do not individually animate titles, cards, lists, images |
| **No interaction effects** | No hover, no click feedback |
| **No ambient backgrounds** | Content pages stay clean |

---

## Effect Options

### Entrance Animations

| Element Type | Effect |
|--------------|--------|
| Full page | Fade |
| Title (cover/ending only) | Float Up, Fade In |

### Ambient Animations (Cover/Ending Only)

| Type | Effect |
|------|--------|
| Background | Particles, Gradient Flow, Texture |
| Decorations | Floating Shapes, Floating Icons |

---

## Implementation Specifications

### CDN

```html
<script src="https://cdn.jsdelivr.net/npm/gsap@3.12.5/dist/gsap.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/tsparticles@2.12.0/tsparticles.bundle.min.js"></script>
```

### Code Structure

```javascript
document.addEventListener('DOMContentLoaded', () => {
  // Full page fade in
  gsap.fromTo('.slide-content',
    { opacity: 0 },
    { opacity: 1, duration: 0.6 }
  );
});
```

### Cover Title Entrance

```javascript
gsap.fromTo('.cover-title',
  { y: 30, opacity: 0 },
  { y: 0, opacity: 1, duration: 0.8 }
);
```

---

## Key Rules

1. **Wrap in DOMContentLoaded** — Ensure DOM is fully loaded
2. **Use GSAP exclusively** — No CSS transition/animation
3. **CSS handles static styles only** — Don't set opacity: 0 or other initial states
4. **Use gsap.fromTo** — Explicitly control start and end states
5. **Use transform (x/y)** — Not top/left
6. **No exit animations** — Entrance only, no departure

---

## Common Issues

### Wrong Approach

```css
/* Setting initial state in CSS - wrong */
.title { opacity: 0; }
```

```javascript
// Then using gsap.to - may conflict
gsap.to('.title', { opacity: 1 });
```

### Correct Approach

```css
/* CSS only sets the final style */
.title { opacity: 1; }
```

```javascript
// Use gsap.fromTo for full control
gsap.fromTo('.title',
  { opacity: 0 },
  { opacity: 1 }
);
```

---

## Content Page Example

```html
<div class="slide-content">
  <h2>Quarterly Performance Summary</h2>
  <ul>
    <li>Revenue growth 25%</li>
    <li>User growth 40%</li>
    <li>Market share increased</li>
  </ul>
</div>

<script>
document.addEventListener('DOMContentLoaded', () => {
  // Only full page fade in, no individual element animations
  gsap.fromTo('.slide-content',
    { opacity: 0 },
    { opacity: 1, duration: 0.6 }
  );
});
</script>
```
