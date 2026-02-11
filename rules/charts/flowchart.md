# Flowcharts & Cycle Diagrams

> Business processes, decision flows, closed-loop cycles

## General Principles

- **Content drives tech choice** — Use HTML+CSS for high-design needs, AntV for standard flows, Mermaid for complex branching
- **3-second rule** — Start point, end point, and flow direction should be immediately clear
- **Visual harmony** — Extract colors and fonts from the page theme for consistency

---

## Use Cases

**Flowcharts**:
- Business processes (Order → Payment → Shipping)
- Decision flows (conditional branching)
- Technical architecture flows

**Cycle diagrams**:
- Closed-loop processes (PDCA, Agile iteration)
- Ecosystem cycles (resource cycles, value chains)
- Periodic stages (product lifecycle)

---

## Approach 1: HTML + CSS (Recommended)

Use when high design quality is required — 100% style control.

### Linear Flow

```html
<div style="display: flex; align-items: center; gap: 16px;">
  <div class="step" style="
    flex: 1; padding: 16px; text-align: center;
    background: #theme-accent-color; color: white; border-radius: 8px;
  ">Requirements Analysis</div>

  <div style="color: #theme-secondary-color; font-size: 20px;">→</div>

  <div class="step" style="
    flex: 1; padding: 16px; text-align: center;
    background: #theme-accent-color; color: white; border-radius: 8px;
  ">Design & Development</div>

  <div style="color: #theme-secondary-color; font-size: 20px;">→</div>

  <div class="step" style="
    flex: 1; padding: 16px; text-align: center;
    background: #theme-accent-color; color: white; border-radius: 8px;
  ">Testing & Launch</div>
</div>
```

### Layout Guidelines

- Use `flex` or `grid` for arrangement — **do not use absolute positioning**
- Use text arrows (→) or `::after` pseudo-elements for connecting arrows
- Equal-width nodes for visual balance
- Use serpentine layout for many steps (refer to [timeline.md](timeline.md))

---

## Approach 2: AntV Infographic

Quick solution for standard flows and cycle diagrams.

### CDN

```html
<script src="https://unpkg.com/@antv/infographic@latest/dist/infographic.min.js"></script>
```

### Basic Usage

```javascript
const { Infographic } = AntVInfographic;
const infographic = new Infographic({
  container: '#container',
  width: '100%',
  height: '100%'
});

const syntax = `
infographic sequence-circular-simple
  data
    items
      - label Plan
        desc Define goals and approach
        icon mdi/clipboard-text
      - label Do
        desc Execute the plan
        icon mdi/play-circle
      - label Check
        desc Evaluate results
        icon mdi/magnify
      - label Act
        desc Optimize and iterate
        icon mdi/refresh
  theme
    palette #theme-color-1 #theme-color-2
`;

infographic.render(syntax);
```

### Common Templates

| Template | Use Case |
|----------|----------|
| `sequence-circular-simple` | Standard cycle (PDCA) |
| `sequence-circular-underline-text` | Text-heavy cycle |
| `list-row-horizontal-icon-arrow` | Horizontal flow |
| `sequence-zigzag-steps-underline-text` | Multi-step serpentine |
| `sequence-roadmap-vertical-simple` | Vertical roadmap |

### Notes

- Optimal node count for cycle diagrams: 3–6; switch to linear layout if over 8
- Add `icon` to each node as a visual anchor
- Inject page theme colors via `theme palette`

---

## Approach 3: Mermaid.js

Use for complex conditional branching.

```html
<script src="https://cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js"></script>

<div class="mermaid">
%%{init: {'themeVariables': {'primaryColor': '#theme-accent-color'}}}%%
graph TD
    A[Start] --> B{Condition}
    B -->|Yes| C[Execute A]
    B -->|No| D[Execute B]
    C --> E[End]
    D --> E
</div>
```

**Note**: Use `%%{init}%%` to override default styles and match page theme.

---

## Selection Quick Reference

| Scenario | Recommended Approach |
|----------|---------------------|
| High design requirements, marketing content | HTML + CSS |
| Standard steps, cycle flows | AntV Infographic |
| Complex conditional branching | Mermaid.js |
