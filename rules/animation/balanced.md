# Balanced Animation Style

> Just the right amount of motion. Noticeable but not distracting.

## Use Cases

- General business occasions
- Internal training / sharing
- Product introductions
- Needs some visual appeal but not excessive

---

## Animation Rules

### Cover / Ending Pages

| Allowed | Effects |
|---------|---------|
| Ambient background | Particles, Gradient Flow, Floating Shapes |
| Title entrance | Float Up, Fade In |

### Content Pages

| Allowed | Prohibited |
|---------|------------|
| Element entrance (Float Up, Fade In, Stagger Fly-In) | Ambient backgrounds |
| Simple hover feedback (Glow, Scale Up, Highlight) | Complex interactions (3D Tilt, Follow Mouse) |
| 1–2 core effects per page | Physics effects |

### Entrance Order

**Top to bottom, left to right**
- Elements at the top of the page enter first
- Within the same row, left elements enter before right ones

---

## Effect Options

### Entrance Animations

| Element Type | Effect |
|--------------|--------|
| Full page | Fade, Slide |
| Title | Float Up, Fade In |
| Lists / Cards | Stagger Fly-In, Float Up |
| Images | Fade In, Zoom In |

### Interaction Animations

| Element Type | Hover Effect |
|--------------|--------------|
| Cards | Glow, Scale Up |
| Images | Scale Up |
| List items | Highlight |

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

### Title Entrance

```javascript
gsap.fromTo('.title',
  { y: 30, opacity: 0 },
  { y: 0, opacity: 1, duration: 0.8 }
);
```

### List Stagger Entrance

```javascript
gsap.fromTo('.list-item',
  { y: 40, opacity: 0 },
  {
    y: 0,
    opacity: 1,
    duration: 0.6,
    stagger: 0.12  // 0.12s delay between items
  }
);
```

### Hover Effects

```javascript
const cards = document.querySelectorAll('.card');
cards.forEach(card => {
  card.addEventListener('mouseenter', () => {
    gsap.to(card, {
      y: -5,
      boxShadow: '0 10px 30px rgba(0,0,0,0.15)',
      duration: 0.3
    });
  });
  card.addEventListener('mouseleave', () => {
    gsap.to(card, {
      y: 0,
      boxShadow: '0 2px 10px rgba(0,0,0,0.1)',
      duration: 0.3
    });
  });
});
```

---

## Key Rules

1. **Wrap in DOMContentLoaded** — Ensure DOM is fully loaded
2. **Use GSAP exclusively** — CSS transitions will conflict with GSAP
3. **CSS handles static styles only** — Don't set animation initial states
4. **Use gsap.fromTo** — Explicitly control start and end states
5. **Entrance order** — Top to bottom, left to right
6. **One controller per element** — Avoid animation conflicts
7. **Use transform (x/y)** — Not top/left
8. **No exit animations** — Entrance only

---

## Content Page Example

```html
<div class="slide">
  <h2 class="title">Product Advantages</h2>
  <div class="cards">
    <div class="card">High Performance</div>
    <div class="card">Easy to Use</div>
    <div class="card">Low Cost</div>
  </div>
</div>

<script>
document.addEventListener('DOMContentLoaded', () => {
  // Title enters first
  gsap.fromTo('.title',
    { y: 30, opacity: 0 },
    { y: 0, opacity: 1, duration: 0.8 }
  );

  // Cards stagger entrance (starts 0.3s after)
  gsap.fromTo('.card',
    { y: 40, opacity: 0 },
    {
      y: 0,
      opacity: 1,
      duration: 0.6,
      stagger: 0.15,
      delay: 0.3
    }
  );

  // Card hover effects
  document.querySelectorAll('.card').forEach(card => {
    card.addEventListener('mouseenter', () => {
      gsap.to(card, { y: -5, scale: 1.02, duration: 0.3 });
    });
    card.addEventListener('mouseleave', () => {
      gsap.to(card, { y: 0, scale: 1, duration: 0.3 });
    });
  });
});
</script>
```

---

## Chart Page Notes

- Charts themselves should **not have interaction animations**
- Entrance animation is allowed (full Fade In)
- Hover effects only for surrounding cards / buttons
