# Theme Customization

> Modify colors, fonts, and decorations based on existing themes, or create custom themes from scratch.

## Change Theme Colors

Keep layout and decoration structure unchanged, replace the entire color palette.

### Steps

1. Extract all color values from current theme templates (`bg-[...]`, `text-[...]`, `border-[...]`)
2. Create a color mapping table:

```
Original → New
#475afe (accent)     → #E53E3E (red)
#292f3b (title)      → #1A202C
#555555 (body text)  → #4A5568
#F3F5F7 (background) → #FFF5F5
gray-400 (secondary) → gray-500
```

3. Global replace across all slide files
4. Check readability after replacement (ensure sufficient contrast)

### Notes

- Accent color changes the most; background and body text colors should be adjusted accordingly
- Maintain sufficient text-to-background contrast
- Decorative element colors follow the accent color

---

## Change Fonts

Replace title or body text fonts.

### Steps

1. Choose a new Google Fonts font
2. Update the font reference in `<link>` tags
3. Update the font-family definition in `<style>`
4. Replace font class names across all slide files

### Example

```html
<!-- Original -->
<link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;600;700&display=swap" rel="stylesheet">
<style>.font-outfit { font-family: Outfit, 'PingFang SC', sans-serif; }</style>

<!-- Changed to -->
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
<style>.font-poppins { font-family: Poppins, 'PingFang SC', sans-serif; }</style>
```

### Notes

- Keep Chinese fallback fonts `'PingFang SC', sans-serif`
- Confirm the new font supports required weights (Light, Regular, Semibold, Bold)
- Check if font size needs fine-tuning (different fonts have different visual sizes)

---

## Modify Decorative Elements

Adjust decorative lines, dots, background shapes, and other decorative elements.

### Modifiable Items

| Element | How to Modify |
|---------|---------------|
| Accent lines | Change width, height, color, border radius |
| Dots | Change size, color, shape (circle → square) |
| Background decorations | Change shape, position, opacity |
| Dividers | Add or remove |

### Example

```html
<!-- Original accent line -->
<div class="w-20 h-1 bg-[#475afe]"></div>

<!-- Changed to rounded capsule -->
<div class="w-24 h-1.5 bg-[#E53E3E] rounded-full"></div>

<!-- Original dot -->
<div class="w-3 h-3 bg-[#292f3b] rounded-full"></div>

<!-- Changed to square -->
<div class="w-3 h-3 bg-[#1A202C] rounded-sm"></div>
```

---

## Create Variant from Existing Theme

Start from an existing theme and create a style variant.

### Flow

1. Copy theme directory to project locally:

```bash
cp -r assets/themes/simple-blue-business/ ./my-custom-theme/
```

2. Modify as needed:
   - Change colors → See "Change Theme Colors"
   - Change fonts → See "Change Fonts"
   - Change decorations → See "Modify Decorative Elements"

3. Specify the local theme directory during generation

### Use Cases

- User likes a theme's layout but wants different colors
- Need a custom theme matching brand colors
- Minor tweaks to an existing theme

---

## User Custom Theme

User provides HTML template files from scratch.

### Minimum Requirements

User-provided theme directory must include at least:

```
my-theme/
├── page_01.html    # Cover page template
├── page_02.html    # At least one content page template
```

### Generation Flow

1. Read user-provided template files
2. Analyze templates following the style extraction rules in [theme.md](theme.md)
3. Extract colors, fonts, decoration style
4. Generate all slides based on extracted styles

### Notes

- Templates must maintain 1280×720 dimensions
- Recommended that user templates include Tailwind CSS reference
- If template style is incomplete, local themes can supplement missing page types
