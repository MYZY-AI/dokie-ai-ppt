# Theme Usage Guide

> The theme is the core of slide styling. Generated HTML must strictly follow the theme's colors, fonts, and layout style.

## Theme Sources

### Online Themes (Default)

Get theme list and templates via CLI. See [theme-list.md](theme-list.md) for the full list:

```bash
npx dokie-cli themes                      # View all available themes
npx dokie-cli theme <name|id> --json      # Get theme templates
```

### Local Built-in Themes (Reference & Backup)

The Skill includes 3 built-in themes located in `assets/themes/`, used for:
- As generation reference examples (understanding theme structure and style extraction methods)
- Direct use when user specifically requests these themes
- As fallback when CLI is unavailable

| Directory | Name | Style |
|-----------|------|-------|
| `assets/themes/dokie-vibe/` | Dokie Vibe | Brand-versatile, strong design sense |
| `assets/themes/simple-blue-business/` | Simple Blue Business | Business blue, conservative and professional |
| `assets/themes/art-education/` | Art Education Presentation | Lively and bold, colorful |

### User Custom Themes

Users can place their own HTML templates in a local directory and use them directly as themes. They just need to follow the theme directory structure.

See [theme-customize.md](theme-customize.md) for details.

---

## Theme Directory Structure

```
theme_name/
├── meta.json           # Theme metadata
├── page_01.html        # Cover page template
├── page_02.html        # Table of contents template
├── page_03.html        # Content page template
├── page_04.html        # Other layout templates
└── ...
```

### meta.json

```json
{
  "id": 8072,
  "name": "Simple Blue Business Style",
  "theme_id": "system_8072",
  "description": "Designed for business plan...",
  "page_count": 7,
  "cover_image": "https://...",
  "screenshots": ["https://...", ...]
}
```

---

## HTML Template Structure

### Base Skeleton

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="utf-8">
    <meta content="width=1280, initial-scale=1.0" name="viewport">
    <title>Page Title</title>

    <!-- Tailwind CSS -->
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4.1.13/dist/index.global.min.js"></script>

    <!-- Theme Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=ThemeFont&display=swap" rel="stylesheet">

    <!-- Theme Custom Styles -->
    <style>
        .font-outfit { font-family: Outfit, 'PingFang SC', sans-serif; }
        .font-inter { font-family: Inter, 'PingFang SC', sans-serif; }
        /* Other theme-specific styles */
    </style>
</head>

<body class="min-h-screen flex items-center justify-center bg-[theme-bg-color] font-[theme-font]">
    <div class="slide-container relative flex flex-col w-[1280px] h-[720px] max-w-[1280px] max-h-[720px] aspect-[16/9] overflow-hidden bg-[theme-bg-color]">

        <!-- Background decoration layer -->
        <div class="absolute inset-0 pointer-events-none z-0">
            <!-- Decorative elements (lines, shapes, etc.) -->
        </div>

        <!-- Content container -->
        <div class="relative z-10 flex flex-col w-full h-full p-[60px]">

            <!-- Title area -->
            <header class="flex flex-col gap-4">
                <h1 class="text-[theme-title-color] text-[42px] font-semibold font-outfit">
                    Title Content
                </h1>
                <!-- Accent line -->
                <div class="w-20 h-1 bg-[theme-accent-color]"></div>
            </header>

            <!-- Main content area -->
            <main class="flex-1 flex gap-12 items-center py-10">
                <!-- Actual content -->
            </main>

            <!-- Footer -->
            <footer class="flex justify-between items-center pt-[17px] w-full">
                <p class="text-gray-400 text-base font-light">Project Name</p>
                <p class="text-gray-400 text-base font-light">Page Number</p>
            </footer>

        </div>
    </div>
</body>
</html>
```

---

## Key Styles to Extract from Theme

### 1. Color Scheme

| Purpose | Extract from Theme |
|---------|--------------------|
| Background color | `bg-[...]` on `body` and `.slide-container` |
| Title color | `text-[...]` on `<h1>` |
| Body text color | `text-[...]` on `<p>` |
| Accent color | Color of decorative lines, icons, links |
| Secondary color | Color of footer, labels |

**Example** (Simple Blue Business Style):
```
Background: #F3F5F7
Title: #292f3b
Body text: #555555
Accent: #475afe
Secondary: gray-400
```

### 2. Fonts

Extract from `<style>` tags and Google Fonts links:

```css
.font-outfit { font-family: Outfit, 'PingFang SC', sans-serif; }
.font-inter { font-family: Inter, 'PingFang SC', sans-serif; }
```

**Usage rules**:
- Titles: Use the theme's title font (e.g., `font-outfit`)
- Body text: Use the theme's body font (e.g., `font-inter`)

### 3. Spacing and Layout

| Property | Common Values |
|----------|---------------|
| Container padding | `p-[60px]` |
| Element gap | `gap-4`, `gap-8`, `gap-12` |
| Title-to-accent-line gap | `gap-4` |

### 4. Decorative Elements

- **Accent lines**: `<div class="w-20 h-1 bg-[accent-color]"></div>`
- **Dots**: `<div class="w-3 h-3 bg-[color] rounded-full"></div>`
- **Background decorations**: Bottom lines, corner shapes, etc.

---

## Steps to Generate a New Page

### Step 1: Choose Reference Template

Select the closest theme template based on page type:

| Page Type | Choose Template |
|-----------|-----------------|
| Cover page | page_01.html |
| Table of contents | page_02.html (usually TOC) |
| Content page | page_03.html or page_04.html |
| Ending page | Last page_xx.html |

### Step 2: Extract Styles

Extract from the reference template:
1. Head section (CSS, fonts) — copy entirely
2. Background decoration layer structure
3. Color values
4. Font class names
5. Spacing values
6. Footer structure

### Step 3: Fill Content

Fill according to the outline's Content:
- Title → `<h1>`
- SubTitle → `<p>` or subheading
- Content list → `<ul>` or card layout
- Kicker → Emphasized text block
- Charts → Chart.js charts
- Images → `<img>` tags

### Step 4: Apply Design

Adjust layout according to the outline's Design description:

| Design Description | Implementation |
|--------------------|----------------|
| Title on left, content on right | `flex` + left header + right main |
| Two-column layout | `flex` + `flex-1` + `flex-1` |
| Image left, text right | `flex` + left img + right text |
| Card grid | `grid grid-cols-3 gap-6` |
| Centered layout | `flex flex-col items-center justify-center` |

---

## Key Constraints

### Must Keep Consistent

| Element | Description |
|---------|-------------|
| Color scheme | Strictly use theme colors, no custom colors allowed |
| Fonts | Only use font classes defined by the theme |
| Decoration style | Accent lines, dots, etc. must match the theme |
| Footer | Maintain the theme's footer structure |

### May Adjust

| Element | Description |
|---------|-------------|
| Font size | May adjust to fit content length |
| Spacing | May fine-tune to prevent overflow |
| Layout | May create new layouts within the theme's style |

### Prohibited

| Prohibited Item | Reason |
|-----------------|--------|
| Custom colors | Breaks theme consistency |
| Changing fonts | Must use theme fonts |
| Removing decorations | Preserves theme identity |
| Changing dimensions | Must be 1280×720 |

---

## Example: Generating a Content Page Based on Theme

### Input

**Outline**:
```
# Page 4. Product Advantages
- Title: Core Product Advantages
- Content:
    - High Performance: Processing speed improved by 300%
    - Easy to Use: Zero learning curve
    - Low Cost: Save 50% on operating expenses
- Design: Title area on the left, three cards stacked vertically on the right
```

### Output

```html
<!-- Generated based on Simple Blue Business Style theme -->
<main class="flex-1 flex gap-12 items-center py-10">

    <!-- Left title area -->
    <div class="w-[300px] flex-shrink-0">
        <h2 class="text-[#475afe] text-xl font-black font-outfit tracking-[2px]">
            ADVANTAGES
        </h2>
        <p class="text-[#292f3b] text-[48px] font-semibold font-outfit leading-tight">
            Core Product Advantages
        </p>
        <div class="w-16 h-1 bg-[#475afe] mt-4"></div>
    </div>

    <!-- Right card list -->
    <div class="flex-1 flex flex-col gap-6">

        <div class="flex gap-4 items-start">
            <div class="w-3 h-3 flex-shrink-0 mt-2.5 bg-[#292f3b] rounded-full"></div>
            <div class="flex flex-col gap-1">
                <h3 class="text-[#475afe] text-2xl font-semibold font-outfit">High Performance</h3>
                <p class="text-[#555555] text-lg font-light">Processing speed improved by 300%</p>
            </div>
        </div>

        <div class="flex gap-4 items-start">
            <div class="w-3 h-3 flex-shrink-0 mt-2.5 bg-[#292f3b] rounded-full"></div>
            <div class="flex flex-col gap-1">
                <h3 class="text-[#475afe] text-2xl font-semibold font-outfit">Easy to Use</h3>
                <p class="text-[#555555] text-lg font-light">Zero learning curve</p>
            </div>
        </div>

        <div class="flex gap-4 items-start">
            <div class="w-3 h-3 flex-shrink-0 mt-2.5 bg-[#292f3b] rounded-full"></div>
            <div class="flex flex-col gap-1">
                <h3 class="text-[#475afe] text-2xl font-semibold font-outfit">Low Cost</h3>
                <p class="text-[#555555] text-lg font-light">Save 50% on operating expenses</p>
            </div>
        </div>

    </div>
</main>
```

Notes:
- All colors come from the theme (`#475afe`, `#292f3b`, `#555555`)
- Font classes come from the theme (`font-outfit`)
- Decorative elements (dots, accent lines) match the theme
- Spacing references theme templates (`gap-4`, `gap-6`)
