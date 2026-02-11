# Quadrant Chart

> Two-dimensional classification analysis, priority matrix, positioning analysis

## General Principles

- **Content drives form** — Understand the user's two dimensions first, then design the quadrant
- **3-second rule** — The meaning of all four quadrants and data point distribution should be immediately clear
- **Visual harmony** — Extract colors from the page theme; quadrant should blend seamlessly with page style

---

## Use Cases

- Important / Urgent matrix (priority)
- BCG matrix (Star / Cash Cow / Question Mark / Dog)
- SWOT analysis
- Risk / Reward analysis
- Cost / Value assessment
- Product / Project positioning

---

## Technical Approach

**HTML + CSS Grid**

### Basic Quadrant Chart

```html
<div class="quadrant" style="
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr 1fr;
  width: 500px;
  height: 400px;
  position: relative;
">
  <!-- Y axis -->
  <div style="
    position: absolute; left: 50%; top: 5%; bottom: 5%;
    width: 2px; background: #theme-secondary-color; transform: translateX(-50%);
  ">
    <div style="position: absolute; top: -8px; left: -4px; border-left: 5px solid transparent; border-right: 5px solid transparent; border-bottom: 8px solid #theme-secondary-color;"></div>
  </div>

  <!-- X axis -->
  <div style="
    position: absolute; top: 50%; left: 5%; right: 5%;
    height: 2px; background: #theme-secondary-color; transform: translateY(-50%);
  ">
    <div style="position: absolute; right: -8px; top: -4px; border-top: 5px solid transparent; border-bottom: 5px solid transparent; border-left: 8px solid #theme-secondary-color;"></div>
  </div>

  <!-- Quadrant 1: Top-right -->
  <div style="grid-column: 2; grid-row: 1; padding: 20px; display: flex; flex-direction: column; align-items: center; justify-content: center;">
    <h3 style="color: #theme-accent-color; font-weight: 600;">Stars</h3>
    <p style="color: #theme-body-color; text-align: center;">High growth + High share</p>
  </div>

  <!-- Quadrant 2: Top-left -->
  <div style="grid-column: 1; grid-row: 1; padding: 20px; display: flex; flex-direction: column; align-items: center; justify-content: center;">
    <h3 style="color: #theme-title-color; font-weight: 600;">Question Marks</h3>
    <p style="color: #theme-body-color; text-align: center;">High growth + Low share</p>
  </div>

  <!-- Quadrant 3: Bottom-left -->
  <div style="grid-column: 1; grid-row: 2; padding: 20px; display: flex; flex-direction: column; align-items: center; justify-content: center;">
    <h3 style="color: #theme-secondary-color; font-weight: 600;">Dogs</h3>
    <p style="color: #theme-body-color; text-align: center;">Low growth + Low share</p>
  </div>

  <!-- Quadrant 4: Bottom-right -->
  <div style="grid-column: 2; grid-row: 2; padding: 20px; display: flex; flex-direction: column; align-items: center; justify-content: center;">
    <h3 style="color: #theme-title-color; font-weight: 600;">Cash Cows</h3>
    <p style="color: #theme-body-color; text-align: center;">Low growth + High share</p>
  </div>
</div>

<!-- Axis labels -->
<div style="display: flex; justify-content: space-between; width: 500px;">
  <span style="color: #theme-body-color;">Low share</span>
  <span style="color: #theme-body-color;">High share</span>
</div>
```

---

## Layout Guidelines

| Guideline | Description |
|-----------|-------------|
| Four equal quadrants | 2×2 Grid, cross axes centered |
| Clear axis labels | Labels at both ends of X and Y axes |
| Axis arrows | X axis points right, Y axis points up, indicating positive direction |
| Axis line length | Don't extend to container edges; leave space for labels |
| Quadrant titles | One short title per quadrant (e.g., "Stars", "Cash Cows") |
| Data points | Use absolute positioning to accurately reflect two-dimensional values |

---

## Data Point Positioning

To place specific data points within quadrants:

```html
<div style="
  position: absolute;
  left: 70%; top: 20%;  /* Calculate percentage position based on data values */
  width: 40px; height: 40px;
  border-radius: 50%;
  background: #theme-accent-color;
  display: flex; align-items: center; justify-content: center;
  color: white; font-size: 12px;
">A</div>
```

- Data point size can represent a third dimension (e.g., market size)
- Optimal data point count: 5–10
- Position must accurately reflect two-dimensional values

---

## SWOT Variant

SWOT doesn't need axis lines and arrows — a four-card grid is sufficient:

```html
<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 12px;">
  <div style="background: rgba(theme-color-1, 0.1); padding: 20px; border-radius: 8px;">
    <h3 style="color: #theme-color-1;">S Strengths</h3>
    <ul><!-- Content --></ul>
  </div>
  <div style="background: rgba(theme-color-2, 0.1); padding: 20px; border-radius: 8px;">
    <h3 style="color: #theme-color-2;">W Weaknesses</h3>
    <ul><!-- Content --></ul>
  </div>
  <div style="background: rgba(theme-color-3, 0.1); padding: 20px; border-radius: 8px;">
    <h3 style="color: #theme-color-3;">O Opportunities</h3>
    <ul><!-- Content --></ul>
  </div>
  <div style="background: rgba(theme-color-4, 0.1); padding: 20px; border-radius: 8px;">
    <h3 style="color: #theme-color-4;">T Threats</h3>
    <ul><!-- Content --></ul>
  </div>
</div>
```

---

## Notes

- Quadrant titles should be concise and instantly understandable
- Four quadrants don't necessarily need different colors, but must blend with page style
- Axis lines and arrows must not overlap with text; leave sufficient spacing
- Data point positions must be accurate — no arbitrary placement
