# Theme List

## Local Themes (No CLI required, ready to use)

| ID | Name | Style | Templates | Local Path |
|----|------|-------|-----------|------------|
| 5100 | Dokie Vibe | Brand-versatile, strong design sense | 15 | `assets/themes/dokie-vibe/` |
| 8072 | Simple Blue Business Style | Business blue, conservative and professional | 7 | `assets/themes/simple-blue-business/` |
| 45696 | Art Education Presentation | Lively and bold, colorful | 10 | `assets/themes/art-education/` |

---

## Online Themes (Fetched via CLI)

Use `npx dokie-cli theme <name|id> --json` to get templates.

### Business / Reports

| ID | Name | Use Case |
|----|------|----------|
| 8073 | Green Modern Work Summary | Work summary, modern green style |
| 8080 | Yellow Team Strategy | Team strategy, vibrant yellow tone |
| 66576 | Finance Business Plan | Financial business plan, conservative and professional |
| 68930 | Business Style Work Summary | Business work summary, conservative style |
| 8078 | Mint Health Pitch | Healthcare business plan, mint green |

### Technology / Industry

| ID | Name | Use Case |
|----|------|----------|
| 38963 | Technology Company Deck | Tech company roadshow |
| 67403 | AI Summit Presentation | AI / tech summit |
| 57602 | New Energy Vehicle Report | New energy industry report |
| 8075 | Simple Grey Industry Report | Industry report, grey minimalist |
| 8079 | Black Industry Report | Industry report, black and bold |
| 51093 | Black Industry Trend Report | Industry trend report, dark professional |
| 9647 | Clipart Trend Report | Trend report, illustration style |

### Education / Academic

| ID | Name | Use Case |
|----|------|----------|
| 8070 | Simple Academic Research | Academic research, minimalist |
| 37617 | Professional Academic Report | Academic report, professional |
| 8076 | Classic University Courseware | University courseware, classic style |
| 46363 | Children Education Courseware | Children's education courseware |
| 23923 | Fresh Student Demonstration | Student presentation, fresh style |

### Design / Creative

| ID | Name | Use Case |
|----|------|----------|
| 8077 | High-end Product Design Plan | High-end product design proposal |
| 48463 | Fashion Marketing Plan | Fashion marketing plan, magazine style |
| 8071 | Magazine Style Personal Introduction | Magazine-style personal introduction |
| 51094 | Illustration Style Self Introduction | Illustration-style self introduction |

### Medical / Professional

| ID | Name | Use Case |
|----|------|----------|
| 68112 | Medical Project Proposal | Medical project proposal |

---

## Theme Recommendation Logic

Auto-recommend based on user needs:

| User Scenario | Recommended Theme |
|---------------|-------------------|
| No specific preference | Dokie Vibe (local) |
| Business report / Investors | Simple Blue Business (local) or Finance Business Plan |
| Education / Training | Art Education (local) or Classic University Courseware |
| Technology / AI | Technology Company Deck or AI Summit Presentation |
| Creative / Design | High-end Product Design Plan or Fashion Marketing Plan |
| Children | Children Education Courseware |
