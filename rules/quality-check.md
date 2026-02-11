# Quality Check

> Post-generation checklist before preview

## Check Flow

After generating all slides, check the following items one by one. Fix issues immediately upon discovery. Prompt user to preview only after all checks pass.

---

## 1. Content Completeness

| Check Item | Description |
|------------|-------------|
| Page count match | Number of generated slides matches the outline page count |
| Content correspondence | Each page's content strictly matches outline Content — nothing missing, nothing extra |
| Chart implementation | Pages marked with Charts in the outline have charts correctly generated |
| Diagram implementation | Pages marked with Diagrams in the outline have diagrams correctly generated |
| Cover / Ending | First page is cover, last page is ending, each appears exactly once |

---

## 2. Visual Overflow

The most common issue. Every page must display completely within 1280×720.

| Check Item | Fix Method |
|------------|------------|
| Text overflows container | Reduce font size (body min 14px, title min 24px) |
| Content breaks layout | Reduce padding / gap, or adjust flex ratios |
| Chart gets clipped | Shrink chart container size, adjust legend position |
| Image overflows | Check `object-fit: cover` and container constraints |
| Long title wraps abnormally | Add `leading-tight`, or reduce font size |

**Quick detection**: Focus on the 2–3 pages with the most content — they are most likely to overflow.

---

## 3. Theme Consistency

| Check Item | Description |
|------------|-------------|
| Colors | All pages use the same theme color palette, no custom colors |
| Fonts | Title and body fonts match the theme |
| Decorations | Decorative lines, dots, background elements are visually consistent |
| Footer | Footer structure is consistent across all pages |
| Adjacent pages | Neighboring pages do not use the exact same template layout |

---

## 4. Group Consistency

Pages within the same group should have:
- Same layout structure
- Consistent title position and font size
- Consistent card / list styles
- Consistent spacing and alignment

---

## 5. Technical Specifications

| Check Item | Description |
|------------|-------------|
| Complete HTML | Each file has a complete `<!DOCTYPE html>` ... `</html>` |
| CDN references | Pages using Chart.js / Font Awesome / GSAP have corresponding CDN links in head |
| No Emoji | No emoji symbols in any file |
| No fabricated images | No AI-fabricated image URLs |
| File naming | `slide_01.html`, `slide_02.html` numbered sequentially |

---

## 6. Animation Check (if applicable)

| Check Item | Description |
|------------|-------------|
| GSAP only | No CSS transition / animation |
| fromTo control | Use `gsap.fromTo` with explicit start and end states |
| DOMContentLoaded | Animation code wrapped in event listener |
| Elements visible at end | All content lands at correct position after entrance animation |
| Style match | Minimal mode content pages have no element-level animations; Balanced mode has no complex interactions |

---

## Check Complete

After all checks pass, prompt user:

```bash
npx dokie-cli preview ./my-project/
```
