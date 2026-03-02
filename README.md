<p align="right">
  <a href="README_CN.md">中文</a> | English
</p>

<p align="center">
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/Logo%20Mark%20Cricle.png" alt="Dokie" width="100" />
</p>

<h1 align="center">Dokie AI PPT Skill</h1>

<p align="center">
  Talk to your AI agent, get professional HTML slides.<br/>
  Built by <a href="https://dokie.ai">dokie.ai</a>
</p>

<p align="center">
  <a href="#quick-start">Quick Start</a> · <a href="#features">Features</a> · <a href="#see-it-in-action">See It in Action</a> · <a href="#go-further-with-dokie">Go Further with Dokie</a>
</p>

<p align="center">
  Works with Claude Code, Cursor, Codex, and 35+ AI agents — any agent that supports the <a href="https://github.com/nicepkg/skills">open skills</a> ecosystem.
</p>

---

## Quick Start

**Install the skill:**

```bash
npx skills add MYZY-AI/dokie-ai-ppt
```

**Ask your agent to create a presentation:**

```
"Make a quarterly report presentation"
"Create a pitch deck for my startup"
"Build a product launch presentation with creative animations"
```

The skill walks you through each step — collect requirements, pick a theme, review the outline, generate slides, and preview. You stay in control at every step.

<details>
<summary>Specify an agent</summary>

```bash
npx skills add MYZY-AI/dokie-ai-ppt -a claude-code
npx skills add MYZY-AI/dokie-ai-ppt -a cursor
```

</details>

<details>
<summary>Prerequisites</summary>

```bash
npx dokie-cli themes    # Verify Dokie CLI is available
```

</details>

---

## Features

### 25+ Themes

From business to medical, tech to creative — choose a built-in theme or customize colors, fonts, and decorations to match your brand. Every theme comes with a complete style system including typography, color palette, backgrounds, and decorative elements.

<p align="center">
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/dokietheme.png" width="260" />
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/market.png" width="260" />
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/medi.png" width="260" />
</p>
<p align="center">
  <em>Left: Dokie brand theme &nbsp;·&nbsp; Center: Market analysis theme &nbsp;·&nbsp; Right: Medical professional theme</em>
</p>

<p align="center">
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/qinghua.png" width="260" />
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/trends.png" width="260" />
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/yellow.png" width="260" />
</p>
<p align="center">
  <em>Left: Chinese porcelain style &nbsp;·&nbsp; Center: Trends & data theme &nbsp;·&nbsp; Right: Warm creative theme</em>
</p>

### 10+ Chart Types

Bar, line, pie, radar, bubble, pyramid, funnel, timeline, flowchart, quadrant — all rendered live in HTML with Chart.js. No static images, no screenshots — real interactive charts embedded directly in your slides. Data updates? Just change the numbers and refresh.

<p align="center">
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/005.png" width="260" />
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/006.png" width="260" />
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/007.png" width="260" />
</p>
<p align="center">
  <em>Bar · Line · Doughnut &nbsp;|&nbsp; Radar · Bubble &nbsp;|&nbsp; Funnel · Pyramid</em>
</p>
<p align="center">
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/008.png" width="260" />
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/009.png" width="260" />
</p>
<p align="center">
  <em>Timeline · Quadrant &nbsp;|&nbsp; Flowchart · Cycle Diagram</em>
</p>

### 3 Animation Styles

Every slide comes alive with GSAP-powered animations. Choose the intensity that matches your presentation:

- **Minimal** — Subtle fade and slide transitions. Clean and professional, perfect for corporate and business presentations where content speaks for itself.

- **Balanced** — Moderate entrance effects with staggered timing. Adds visual rhythm without overwhelming the audience. Great for product demos and team meetings.

- **Creative** — Bold cinematic sequences with scroll-triggered effects, parallax layers, and dynamic transitions. Designed for keynotes, pitches, and presentations that need to impress. Think Awwwards-level motion design.

<p align="center">
  <a href="https://www.dokie.ai/presentation/share/azVPjJDBaPgM">
    <img src="https://github.com/user-attachments/assets/85a9a3a3-5054-48b4-826f-209e3456e0f9" width="680" />
  </a>
</p>
<p align="center">
  <em>Creative animation style — cinematic entrance effects with layered transitions. <a href="https://www.dokie.ai/presentation/share/azVPjJDBaPgM">Click to view live demo →</a></em>
</p>

### Auto Quality Check

After generation, the skill automatically reviews every slide for:
- **Content overflow** — text or elements bleeding outside the slide boundaries
- **Chart rendering** — ensuring all data visualizations display correctly
- **Theme consistency** — verifying fonts, colors, and spacing match the selected theme

Issues are fixed before you even notice them. You get polished results from the first preview.

---

## See It in Action

Generated slides are previewed instantly. The preview server gives you two links — a local one for yourself and a public one you can share with anyone.

<p align="center">
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/preview.jpg" width="680" />
</p>
<p align="center">
  <em>Built-in preview — browse all slides, check layouts, share with your team via public link</em>
</p>

---

## Go Further with Dokie

Want more control? Every presentation you generate can be opened in [dokie.ai](https://dokie.ai) for free. Inside the Dokie editor, you can:

- Fine-tune layouts, text, and visual details with a drag-and-drop editor
- Adjust styles, colors, and fonts at a granular level
- Export to **PDF**, **PPTX**, **images**, and more

From AI generation to pixel-perfect polish — all in one workflow.

<p align="center">
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/edit.png" width="330" />
  <img src="https://skill-1317512395.cos.ap-singapore.myqcloud.com/editdaochu.png" width="330" />
</p>
<p align="center">
  <em>Left: Fine-tune every detail in the Dokie editor &nbsp;·&nbsp; Right: Export to PDF, PPTX and more</em>
</p>

---

<p align="center">
  <a href="https://dokie.ai">dokie.ai</a> · MIT License
</p>
