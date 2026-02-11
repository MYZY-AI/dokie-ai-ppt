<p align="center">
  <img src="./Logo%20Mark%20Cricle.png" alt="Dokie" width="120" />
</p>

<h1 align="center">Dokie AI PPT Skill</h1>

<p align="center">
  Professional AI presentation generation skill by <a href="https://dokie.ai">dokie.ai</a><br/>
  Create stunning HTML slides through conversation — from minimal business style to Awwwards-level creative motion.
</p>

Built on web technologies (Tailwind CSS, Chart.js, GSAP, Font Awesome), far beyond what traditional PPT can deliver.

## Install

```bash
npx skills add MYZY-AI/dokie-ai-ppt
```

Install to a specific agent:

```bash
npx skills add MYZY-AI/dokie-ai-ppt -a claude-code
npx skills add MYZY-AI/dokie-ai-ppt -a cursor
```

## Usage

Once installed, simply ask your agent to create a presentation:

- "Make a quarterly report presentation"
- "Create a pitch deck for my startup"
- "Build a product launch presentation with creative animations"

The skill will guide the agent through:

1. **Collect requirements** — topic, audience, page count, style, animation preference
2. **Select theme** — 25+ themes across business, tech, education, creative, and medical categories
3. **Generate outline** — structured content with layout suggestions per page
4. **Generate HTML slides** — fully styled, theme-consistent HTML files
5. **Preview** — local preview via `npx dokie-cli preview`

## Prerequisites

```bash
npx dokie-cli themes    # Verify Dokie CLI is available
```

## Features

- **25+ Themes** — Business, tech, education, creative, medical styles + 3 local built-in themes
- **Theme Customization** — Change colors, fonts, decorations, or create variants
- **6 Chart Types** — Bar/Line/Pie/Radar/Bubble (Chart.js), Pyramid, Funnel, Timeline, Flowchart, Quadrant
- **3 Animation Styles** — Minimal, Balanced, Creative (GSAP-powered)
- **Quality Checks** — Content completeness, overflow detection, theme consistency
- **Modification Scenarios** — Insert, delete, split, merge, restyle, reorder pages

## Specs

| Item | Value |
|------|-------|
| Resolution | 1280 × 720 |
| Charts | Chart.js 4.5 |
| Icons | Font Awesome 6.5 |
| Animation | GSAP 3.12 |
| CSS | Tailwind CSS 4.1 |

## License

MIT
