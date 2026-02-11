# Creative Animation Style

> Awwwards-level web presentations. Aesthetic benchmarks: Godly.website, The FWA, Codrops.

## Use Cases

- Product launches
- Creative / design showcases
- Brand promotions
- Occasions requiring visual impact

---

## Core Principles

1. **Creative ≠ more animation** — It's about deep integration of animation and content, not piling on decorations
2. **Effect keywords are directions, not commands** — The same "Particles" should look completely different for ocean / tech / business themes
3. **Content drives details** — Automatically choose colors, speed, shapes based on the topic
4. **Elements must be visible at the end** — After entrance animation completes, content must land at the correct position
5. **No CSS animation** — Use GSAP or specified libraries exclusively

---

## Animation Classification

### 1. Entrance

| Sub-category | Effects |
|--------------|---------|
| Text | Float Up, Typewriter, Letter Fly In |
| Images | Stagger Fly-In, Fade In, Zoom In |
| Data | Count Up, Chart Grow |
| Full page | Fade, Push Pull, Slide |

### 2. Interaction

| Sub-category | Effects |
|--------------|---------|
| Hover | Glow, Scale Up, 3D Tilt, Follow Mouse, Highlight |
| Click | Bounce, Ripple, Expand |
| Linked | Hover & Show, Scene Switch, Sync Reveal |

### 3. Atmosphere

| Sub-category | Effects |
|--------------|---------|
| Full-screen background | Particles, Gradient Flow, Texture, Spotlight |
| Decorative elements | Floating Icons, Scrolling Text, Floating Shapes |
| Cursor | Custom Cursor, Cursor Trail |

### 4. Advanced

| Sub-category | Effects |
|--------------|---------|
| 3D | 3D Tour (Sketchfab) |
| Physics | Gravity, Collision |
| Creative | Code Sketch, Mini App |

---

## Scene Strategies

### Cover / Quote Pages

**Combo**: Ambient background + Entrance animation

| Theme | Recommended Combo |
|-------|-------------------|
| Ocean / Nature | Particles (bubbles) + Float Up + Cursor Trail |
| Tech / Future | Particles (network lines) + Typewriter + Custom Cursor |
| Minimal / Business | Gradient Flow + Float Up + Floating Shapes |

### Data / Chart Pages

**Combo**: Data entrance + Linked feedback

| Scene | Recommended Combo |
|-------|-------------------|
| Revenue trends | Count Up + Chart Grow + Glow + Hover & Show |
| Relationship networks | Chart Grow + Highlight + Sync Reveal |

### Product / 3D Pages

**Combo**: 3D / Physics + Clean atmosphere

| Scene | Recommended Combo |
|-------|-------------------|
| Product showcase | 3D Tour + Stagger Fly-In + Hover & Show |
| Concept visualization | Gravity / Collision + Follow Mouse |

### Directory / List Pages

**Combo**: Staggered entrance + Hover feedback

| Scene | Recommended Combo |
|-------|-------------------|
| Team / Cards | Stagger Fly-In + 3D Tilt + Glow |
| Timeline | Stagger Fly-In + Expand + Highlight |

---

## Theme → Visual Mapping

| Theme | Colors | Speed | Shapes | Atmosphere |
|-------|--------|-------|--------|------------|
| Ocean / Nature | Blue-green | Slow, fluid | Circles, waves | Calm |
| Tech / Future | Cool white / Blue-purple | Fast, sharp | Triangles, lines | Precise |
| Business / Formal | Grey / Dark blue | Very slow, restrained | Geometric, grid | Steady |
| Art / Creative | Colorful gradients | Rhythmic | Irregular | Expressive |
| Warm / Humanistic | Warm yellow-orange | Slow, breathing | Rounded, soft | Approachable |

---

## CDN Resources

```html
<!-- Core -->
<script src="https://cdn.jsdelivr.net/npm/gsap@3.12.5/dist/gsap.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/tsparticles@2.12.0/tsparticles.bundle.min.js"></script>

<!-- Data animations -->
<script src="https://cdn.jsdelivr.net/npm/countup.js@2.8.0/dist/countUp.umd.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/chart.js@4.5.0/dist/chart.umd.js"></script>

<!-- Text effects -->
<script src="https://cdn.jsdelivr.net/npm/split-type@0.3.4/umd/index.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/typed.js@2.1.0/dist/typed.umd.js"></script>

<!-- Interaction effects -->
<script src="https://cdn.jsdelivr.net/npm/vanilla-tilt@1.8.1/dist/vanilla-tilt.min.js"></script>

<!-- Advanced effects -->
<script src="https://cdn.jsdelivr.net/npm/matter-js@0.19.0/build/matter.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/p5@1.9.0/lib/p5.min.js"></script>
```

---

## Effect Implementation Reference

### Entrance — Text

| Effect | Implementation | Theme Adaptation |
|--------|----------------|------------------|
| Float Up | `gsap.fromTo(el, {y:30, opacity:0}, {y:0, opacity:1})` | Formal → y:30/1s, Playful → y:80/0.5s |
| Typewriter | Typed.js | Tech → blinking cursor, Literary → handwriting font |
| Letter Fly In | SplitType + GSAP stagger | High-impact titles |

### Entrance — Images / Cards

| Effect | Implementation | Theme Adaptation |
|--------|----------------|------------------|
| Stagger Fly-In | `gsap.fromTo(els, {y:40, opacity:0}, {y:0, opacity:1, stagger:0.12})` | 3 items → 0.15s, 10 items → 0.08s |
| Fade In | `gsap.fromTo(el, {opacity:0}, {opacity:1})` | Combine with scale for more depth |
| Zoom In | `gsap.fromTo(el, {scale:0.8, opacity:0}, {scale:1, opacity:1})` | Product enlarges, background shrinks |

### Entrance — Data

| Effect | Implementation | Notes |
|--------|----------------|-------|
| Count Up | CountUp.js | Initialize with `window.onload`, constructor is `countUp.CountUp` |
| Chart Grow | Chart.js animation | duration: 1500 |

### Interaction — Hover

| Effect | Implementation |
|--------|----------------|
| Glow | `gsap.to(el, {y:-5, boxShadow:'...'})` |
| Scale Up | `gsap.to(el, {scale:1.05})` |
| 3D Tilt | vanilla-tilt.js |
| Follow Mouse | GSAP following mouse coordinates |
| Highlight | GSAP color / border change |

### Atmosphere — Particles

| Theme | Color | Shape | Speed | Links |
|-------|-------|-------|-------|-------|
| Ocean | Blue | circle | Slow | false |
| Tech | White | triangle | Fast | true |
| Business | Grey | circle | Very slow | true (sparse) |

---

## Constraints

- Elements **must be visible** after entrance animation ends
- tsParticles particle count **< 100**
- Animations use **transform**, not top/left
- Sketchfab uses URLs provided in the outline
- CountUp.js initializes with `window.onload`
- Chart.js uses real data directly with built-in animation

---

## Common Issues

### gsap.from/to Combination Issues

```javascript
// Wrong: CSS sets opacity:0, then uses gsap.to
// May cause element to stay transparent

// Correct: CSS sets final state, use gsap.from
// Or use gsap.fromTo for full control
gsap.fromTo(el,
  { opacity: 0, y: 30 },   // from
  { opacity: 1, y: 0 }     // to
);
```

---

## Restraint Principle

Even in creative style, maintain restraint:

- **1–2 core animations** + **1 ambient effect**
- Content drives choices (ocean → bubbles, tech → network lines)
- 3D models must be obtained via tools and relate to content
- Physics effect elements must relate to content — no meaningless circles or squares
