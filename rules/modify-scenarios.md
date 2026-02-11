# Modification Scenarios

> Rules for handling user requests to modify existing slides

## Core Principle

**Minimal changes** — Don't touch content the user didn't mention. Changing one page should not affect others. Changing content should not change layout (unless necessary).

---

## Scenario 1: Partial Content Edit

User requests changes to text, data, etc. on a specific page.

**Flow**:
1. Read target `slide_XX.html`
2. Locate the edit point and replace content
3. Check if the edit causes overflow; adjust font size or spacing if needed
4. Write back file

**Examples**:
- "Change the data on page 3 from 1200 to 1500"
- "Change page 5 title to 'Market Strategy Upgrade'"

---

## Scenario 2: Insert New Page

User requests adding a new page at a specific position.

**Flow**:
1. Confirm insertion position and content
2. Generate new page referencing adjacent pages' theme styles
3. Write new file
4. Rename subsequent pages (`slide_05` → `slide_06`, shift accordingly)

**Notes**:
- New page styles must maintain theme consistency with surrounding pages
- If insertion is within a group, the new page must follow the group's style
- Verify total page count after renaming

---

## Scenario 3: Delete Page

User requests removing a page.

**Flow**:
1. Confirm which page to delete
2. Delete the file
3. Rename subsequent pages (fill the numbering gap)

**Notes**:
- Cannot delete the cover page (slide_01) or ending page (last page)
- If user asks to delete cover/ending, confirm whether they mean "delete" or "replace content"

---

## Scenario 4: Split Content

A page has too much content; user requests splitting into multiple pages.

**Flow**:
1. Read the target page
2. Split into 2–3 pages by content logic
3. Split pages use the same theme template (same group)
4. Write new files, rename subsequent pages

**Splitting principles**:
- Split along natural content topic boundaries
- Each page should maintain one core message
- Titles can use "(Part 1)/(Part 2)" or sequence numbers to differentiate

---

## Scenario 5: Merge Pages

User feels some pages are too fragmented and requests merging.

**Flow**:
1. Read the pages to be merged
2. Consolidate content into a single page
3. Check if merged content overflows
4. Delete extra files, rename

**Note**: When overflowing, prioritize reducing font size and spacing. If content still doesn't fit, advise the user to keep them separate.

---

## Scenario 6: Adjust Style

User feels the style is off and requests adjustments.

| User says | Actual operation |
|-----------|-----------------|
| "Make it more lively" | Consider switching animation style (Minimal → Balanced), or adjust layout to be more dynamic |
| "Make it more formal" | Reduce decorations, simplify animation (Creative → Minimal), use more structured layout |
| "Don't like the colors" | Follow theme switching flow, or see [theme-customize.md](theme-customize.md) for color changes |
| "Text too small/large" | Adjust font size, check overall consistency |

---

## Scenario 7: Reorder Pages

User requests rearranging page order.

**Flow**:
1. Confirm the new page order
2. Rename all files according to new order
3. Cover must remain as the first page, ending must remain as the last page

---

## After All Modifications

1. Run relevant checks from [quality-check.md](quality-check.md) on modified pages
2. Prompt user to preview:

```bash
npx dokie-cli preview ./my-project/
```
