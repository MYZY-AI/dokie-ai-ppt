# Workflow

**Important**: This is an interactive workflow. At each step:
1. **Read the referenced rule files** before doing the work — don't skip them
2. **Present your result** to the user and wait for their response before moving on
3. If anything is unclear or ambiguous, ask the user rather than guessing

## New Project

### Step 1: Collect Requirements

Understand user intent and collect the following key information:

| Info | Description |
|------|-------------|
| Topic | Core topic of the PPT |
| Audience | Target audience |
| Pages | Estimated page count (default 8–12) |
| Style | Visual style preference |
| Animation | Minimal / Balanced (default) / Creative |

**Collect flexibly, don't ask rigid questions**:
- One-line request (e.g., "make a quarterly report") → Proactively fill in reasonable defaults, present all at once for confirmation
- User provides extensive content or documents → Extract key info from content, propose structure suggestions
- User already has a clear outline → Skip outline generation, go directly to theme selection and HTML generation
- When info is incomplete, ask follow-up at most once; prefer filling gaps with reasonable defaults

**Page count estimation**:
- Little content → Default 8–12 pages
- Extensive content with clear structure → Set according to structure
- Extensive content without clear structure → Estimate by content density, one topic per page

Present all collected info to user for confirmation. Wait for user to confirm or adjust before moving to the next step.

### Step 2: Select Theme

Get available theme list:

```bash
npx dokie-cli themes
```

Present the theme list to the user and let them choose. After user selects, get theme templates:

```bash
npx dokie-cli theme <name|id> --json
```

Present the selected theme details to the user. Wait for user to confirm the theme before moving on.

See [theme.md](theme.md) for theme style extraction methods.

### Step 3: Generate Outline

**Before generating the outline, read [outline.md](outline.md)** for the outline format specifications.

Generate outline based on requirements and theme. Each page includes Content (content elements) and Design (layout suggestions).

Present the complete outline to the user for review. The user may want to adjust content, page order, or structure — wait for their approval before generating any HTML.

### Step 4: Generate Slides

**Before generating slides, read [theme.md](theme.md) and [slide-html.md](slide-html.md)** to ensure theme consistency and HTML specs compliance.

Create project directory and generate HTML files:

```
my-project/
├── slide_01.html    # Cover page
├── slide_02.html    # Table of contents
├── slide_03.html    # Content page
├── ...
└── slide_XX.html    # Ending page
```

**Analyze grouping before generation**: Check which pages in the outline need visual consistency (sequential content, parallel content, comparison pages, section headers, etc.). Pages in the same group use the same layout template.

**Generation rules**:
- Each file is a complete HTML page (with head / body)
- Strictly follow theme styles (see [theme.md](theme.md))
- Strictly follow outline content (see [slide-html.md](slide-html.md))
- Pages in the same group maintain visual consistency
- **Concurrent generation**: Batch by page order, write multiple files in parallel per round (5 per round, adjust flexibly), minimize the number of rounds

### Step 5: Preview & Check

After generation is complete, immediately open preview:

```bash
npx dokie-cli preview ./my-project/
```

The preview server will return two URLs — present **both** to the user:
- **Local**: `http://localhost:xxxx` — for local access
- **Public**: `https://xxx.trycloudflare.com` — shareable public link

**Before checking quality, read [quality-check.md](quality-check.md)** for the checklist.

After preview launches, check for common issues (content overflow, chart rendering, etc.). If issues are found, fix them and prompt user to refresh.

Wait for user feedback on the preview — the user may request changes.

---

## Modify Project

See [modify-scenarios.md](modify-scenarios.md) for handling various modification scenarios.

### Step 1: Understand Intent

- Clear instructions → Execute directly
- Vague instructions → Ask for confirmation

### Step 2: Minimal Change Principle

| Principle | Description |
|-----------|-------------|
| Only change what's requested | Don't touch content the user didn't mention |
| Preserve layout | Don't change layout (unless content changes affect it) |
| Preserve styles | Keep fonts, colors, spacing as-is |
| Preserve images | Don't change image URLs (unless explicitly asked to swap images) |

### Step 3: Modify Files

1. Read the `slide_XX.html` that needs modification
2. If referencing other page styles, read the corresponding files first
3. Write back after modification

Prompt preview when done (present both Local and Public URLs to the user):

```bash
npx dokie-cli preview ./my-project/
```

---

## Switch Theme

1. Get new theme templates: `npx dokie-cli theme <new-theme> --json`
2. Read each `slide_XX.html` and apply new theme styles
3. **Preserve original content and layout**, only update colors, fonts, background
4. Write back files
