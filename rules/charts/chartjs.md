# Chart.js Statistical Charts

> Bar, line, pie, radar, bubble, and other statistical charts

## General Principles

### 3-Second Rule
The audience should grasp the chart's core message within 3 seconds. Simplify and layer if too much content; supplement or change format if too little.

### Content-Driven
Understand what the user wants to communicate first, then choose the chart type. Charts serve content, not decoration.

### Data Integrity
**Fabricating data is prohibited.** Only use data from the outline or explicitly provided by the user.

### Visual Harmony
Extract colors from the page theme (accent, body text, etc.) to keep charts consistent with the page style. Charts should blend into the page, not feel forced.

---

## Technical Specifications

### CDN

```html
<script src="https://cdn.jsdelivr.net/npm/chart.js@4.5.0/dist/chart.umd.js"></script>
```

### Basic Configuration

```javascript
new Chart(ctx, {
  type: 'bar',
  data: { /* ... */ },
  options: {
    responsive: true,
    maintainAspectRatio: false,
    animation: false,  // Disable animation for slide context
    plugins: {
      legend: { position: 'bottom' }
    }
  }
});
```

### Required Configuration

| Config | Value | Description |
|--------|-------|-------------|
| responsive | true | Responsive layout |
| maintainAspectRatio | false | Allow custom width/height |
| animation | false | Disable in slides (unless animation is needed) |

### Container Size

```html
<div style="width: 600px; height: 400px;">
  <canvas id="myChart"></canvas>
</div>
```

Ensure complete display within 1280×720, leaving space for title and legend.

---

## Bar Chart

**Use cases**: Data comparison, ranking display, time series comparison

### Basic Bar Chart

```javascript
{
  type: 'bar',
  data: {
    labels: ['Product A', 'Product B', 'Product C'],
    datasets: [{
      data: [300, 450, 280],
      backgroundColor: '#theme-accent-color'
    }]
  }
}
```

### Clustered Bar Chart

Multiple dataset comparison, multiple bars per category:

```javascript
{
  type: 'bar',
  data: {
    labels: ['Q1', 'Q2', 'Q3', 'Q4'],
    datasets: [
      { label: '2024', data: [120, 190, 150, 220], backgroundColor: '#theme-color-1' },
      { label: '2025', data: [150, 210, 180, 260], backgroundColor: '#theme-color-2' }
    ]
  }
}
```

### Stacked Bar Chart

Show totals and component proportions:

```javascript
{
  type: 'bar',
  data: {
    labels: ['Q1', 'Q2', 'Q3', 'Q4'],
    datasets: [
      { label: 'Online', data: [80, 100, 90, 120], backgroundColor: '#theme-color-1' },
      { label: 'Offline', data: [40, 90, 60, 100], backgroundColor: '#theme-color-2' }
    ]
  },
  options: {
    scales: {
      x: { stacked: true },
      y: { stacked: true }
    }
  }
}
```

### Horizontal Bar Chart

Use when labels are long:

```javascript
{
  type: 'bar',
  options: { indexAxis: 'y' }
}
```

**Recommendation**: 5–10 data points; consider Top N or grouping if more.

---

## Line Chart

**Use cases**: Trend changes, time series, multi-series comparison

### Basic Line Chart

```javascript
{
  type: 'line',
  data: {
    labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May'],
    datasets: [{
      label: 'Revenue',
      data: [100, 120, 115, 140, 160],
      borderColor: '#theme-accent-color',
      fill: false,
      tension: 0.3
    }]
  }
}
```

### Area Chart

```javascript
{
  type: 'line',
  data: {
    datasets: [{
      data: [100, 120, 115, 140, 160],
      borderColor: '#theme-accent-color',
      backgroundColor: 'rgba(theme-color, 0.1)',
      fill: true
    }]
  }
}
```

### Multi-Series Comparison

```javascript
{
  type: 'line',
  data: {
    labels: ['Q1', 'Q2', 'Q3', 'Q4'],
    datasets: [
      { label: 'Product A', data: [100, 130, 120, 160], borderColor: '#theme-color-1' },
      { label: 'Product B', data: [80, 110, 140, 150], borderColor: '#theme-color-2' }
    ]
  }
}
```

**Recommendation**: Aggregate by quarter/year when there are too many data points to maintain readability.

---

## Pie / Doughnut Chart

**Use cases**: Proportion distribution, composition analysis, market share

```javascript
{
  type: 'doughnut',  // or 'pie'
  data: {
    labels: ['Mobile', 'Desktop', 'Tablet'],
    datasets: [{
      data: [65, 25, 10],
      backgroundColor: ['#theme-color-1', '#theme-color-2', '#theme-color-3']
    }]
  }
}
```

**Recommendation**: 5–7 categories; merge extras into "Other". Doughnut is more modern than pie — prefer it.

---

## Radar Chart

**Use cases**: Multi-dimensional capability comparison, comprehensive assessment, feature analysis

```javascript
{
  type: 'radar',
  data: {
    labels: ['Technology', 'Design', 'Communication', 'Execution', 'Innovation'],
    datasets: [{
      label: 'Team A',
      data: [80, 90, 70, 85, 75],
      borderColor: '#theme-color-1',
      backgroundColor: 'rgba(theme-color-1, 0.2)'
    }]
  }
}
```

**Recommendation**: 5–8 dimensions; ensure sufficient color differentiation for multi-series comparisons.

---

## Bubble Chart

**Use cases**: Three-dimensional data display (X axis, Y axis, bubble size), correlation analysis

```javascript
{
  type: 'bubble',
  data: {
    datasets: [{
      label: 'Product Lines',
      data: [
        { x: 20, y: 30, r: 15 },
        { x: 40, y: 10, r: 10 },
        { x: 15, y: 50, r: 20 }
      ],
      backgroundColor: 'rgba(theme-color, 0.6)'
    }]
  }
}
```

**Recommendation**: Moderate bubble count (5–15), avoid excessive overlap. Size differences should be noticeable.

---

## Chart Selection Quick Reference

| User Intent | Recommended Chart |
|-------------|-------------------|
| Compare values | Bar chart (vertical) |
| Long labels | Bar chart (horizontal) |
| Year-over-year comparison | Clustered bar chart |
| Total + composition | Stacked bar chart |
| Trend over time | Line chart |
| Trend + area feel | Area chart |
| Proportion distribution | Doughnut / Pie chart |
| Multi-dimensional assessment | Radar chart |
| Three-dimensional relationship | Bubble chart |

---

## Common Mistakes

```javascript
// Wrong: Fabricated data
data: [Math.random() * 100, ...]

// Wrong: Too many data points causing clutter
labels: ['Jan', 'Feb', ..., 'Dec']  // 12 months may be too many
```

```javascript
// Correct: Use real data
data: [120, 190, 150, 220]  // From the outline

// Correct: Aggregate by quarter
labels: ['Q1', 'Q2', 'Q3', 'Q4']
```
