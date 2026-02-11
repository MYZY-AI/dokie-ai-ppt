# Timeline

> Development history, project milestones, stage-based event display

## General Principles

- **Content drives form** — Understand content volume and time span first, then choose layout
- **3-second rule** — Time flow direction and key nodes should be immediately recognizable
- **Visual harmony** — Extract colors, fonts, border-radius, shadows from the page theme for consistency

---

## Use Cases

- Company history
- Project milestones
- Product iteration roadmap
- Historical event review

---

## Style Options

Choose based on node count and content length:

| Style | When to Use | Description |
|-------|-------------|-------------|
| **Horizontal linear** | 3–5 nodes, brief content | Most basic, left-to-right layout |
| **Vertical linear** | 3–6 nodes, longer content | Top-to-bottom layout, suitable for detailed descriptions |
| **Serpentine** | 6+ nodes | S-shaped layout, auto-wrapping, maximizes space usage |
| **Fishbone alternating** | 4–8 nodes, with categorical comparison | Alternating placement on both sides of center axis |

---

## Technical Approach

**HTML + CSS Flex / Grid**

### Horizontal Linear Example

```html
<div class="timeline" style="display: flex; align-items: center; gap: 0; position: relative;">

  <!-- Main axis line -->
  <div style="position: absolute; top: 50%; left: 5%; right: 5%; height: 2px; background: #theme-secondary-color;"></div>

  <!-- Node -->
  <div style="flex: 1; display: flex; flex-direction: column; align-items: center; position: relative; z-index: 1;">
    <div style="width: 12px; height: 12px; border-radius: 50%; background: #theme-accent-color;"></div>
    <p style="margin-top: 8px; font-weight: 600; color: #theme-title-color;">2020</p>
    <p style="color: #theme-body-color; text-align: center;">Company founded</p>
  </div>

  <div style="flex: 1; display: flex; flex-direction: column; align-items: center; position: relative; z-index: 1;">
    <div style="width: 12px; height: 12px; border-radius: 50%; background: #theme-accent-color;"></div>
    <p style="margin-top: 8px; font-weight: 600; color: #theme-title-color;">2022</p>
    <p style="color: #theme-body-color; text-align: center;">Series A funding</p>
  </div>

  <div style="flex: 1; display: flex; flex-direction: column; align-items: center; position: relative; z-index: 1;">
    <div style="width: 12px; height: 12px; border-radius: 50%; background: #theme-accent-color;"></div>
    <p style="margin-top: 8px; font-weight: 600; color: #theme-title-color;">2024</p>
    <p style="color: #theme-body-color; text-align: center;">1M users reached</p>
  </div>

</div>
```

### Serpentine

Use Grid for multi-row alternating layout:

```html
<div style="display: grid; grid-template-columns: repeat(4, 1fr); gap: 24px;">
  <!-- Row 1: left → right -->
  <div class="node">2020 Founded</div>
  <div class="node">2021 Product launch</div>
  <div class="node">2022 Series A</div>
  <div class="node">2023 Global expansion</div>

  <!-- Row 2: right → left (use direction: rtl or order to reverse) -->
  <div class="node" style="grid-column: 4;">2024 Series B</div>
  <div class="node" style="grid-column: 3;">2025 IPO</div>
</div>
```

---

## Layout Guidelines

| Guideline | Description |
|-----------|-------------|
| Main axis line | Use `absolute` positioning, spanning all nodes |
| Node dots | Precisely aligned on the axis line, no offset allowed |
| Even distribution | Use `flex: 1` or `grid` for equal spacing |
| Turns | Use arrows or connecting lines to guide the eye in serpentine layout |
| Key nodes | Emphasize with different colors or larger dots |

## Notes

- Keep each node concise: time label + title + brief description
- Time labels should be clear and prominent, bold font weight
- Recommended node count: 3–8; simplify or split pages if more
