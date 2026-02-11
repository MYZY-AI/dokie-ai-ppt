# Outline Specification

## Outline Structure

Each page includes the following elements:

| Element | Description | Required |
|---------|-------------|----------|
| Summary | One-line overview starting with `#`, including page number | Yes |
| Title | Page title | Yes |
| SubTitle | Subtitle (commonly used on cover pages) | No |
| Content | Main body content | Yes |
| Kicker | Key takeaway / conclusion (part of Content) | No |
| Charts | Data chart description (part of Content) | No |
| Diagrams | Flow / diagram description (part of Content) | No |
| Design | Layout suggestion describing the visual structure of the page | Yes |

---

## Format Example

```markdown
# Page 1. Cover Page
- Title: SOL COFFEE
- SubTitle: Premium Coffee Chain Business Plan
- Content:
    - Date: 2026-01
    - Author: Founding Team
- Design: Title centered upper area, subtitle below, overall vertically centered, date and author in small text at bottom

# Page 2. Table of Contents
- Title: Contents
- Content:
    - 1. Market Insights
    - 2. Brand Positioning
    - 3. Product Portfolio
    - 4. Operations Model
    - 5. Financial Projections
- Design: Title on the left, 2-column directory grid on the right

# Page 3. Coffee Market Size
- Title: China's Coffee Market Continues Rapid Growth
- Content:
    - Charts:
        - Market size trend: 2022 ¥120B, 2023 ¥155B, 2024 ¥200B, 2025 ¥250B (estimated)
    - Kicker: CAGR exceeds 25%, specialty segment growing even faster
    - Tier-1 city penetration approaching Western levels; tier-2/3 cities still have huge potential
- Design: Title at top, line chart occupying main area, Kicker highlight block at bottom-right

# Page 4. Consumer Profile
- Title: Target Users — New Urban Coffee Drinkers
- Content:
    - Charts:
        - Age distribution: 25-35 yrs 60%, 18-24 yrs 25%, 36+ yrs 15%
    - Core traits: quality-conscious, willing to pay for experience, active on social media
    - Purchase frequency: 3-5 cups per week, average spend ¥25-40
    - Pain points: chain brands highly homogenized, independent cafés lack consistency
- Design: Doughnut chart on the left, four key-point cards vertically stacked on the right

# Page 5. Brand Positioning
- Title: SOL — Sunshine in Every Cup
- Content:
    - Brand philosophy: Derived from Latin "sun", conveying warmth and vitality
    - Positioning: **The optimal balance between quality and experience**
    - Differentiation: Direct sourcing + in-store roasting + minimalist space design
    - Diagrams: Origin sourcing → 72h delivery → In-store roasting → Handcrafted serving
- Design: Title at top, brand philosophy in large centered text, horizontal flowchart below

# Page 6. Product Portfolio
- Title: Three Product Lines Covering All Scenarios
- Content:
    - Classic line: Americano, Latte, Cappuccino (50% of sales)
    - Seasonal line: 3 limited creative specials per season (30% of sales)
    - Retail line: Drip bags, coffee beans, cold brew (20% of sales)
- Design: Three cards side by side, one product line per card, with icons and percentage data

# Page 7. Single-Store Operations Model
- Title: Single-Store Monthly Revenue Model
- Content:
    - Charts:
        - Revenue breakdown: Dine-in 45%, Delivery 35%, Retail 20%
    - Daily cup output: 300 cups
    - Monthly revenue: ¥270K
    - Gross margin: 65%
    - Payback period: 14 months
- Design: Pie chart showing revenue breakdown on the left, key metrics listed vertically on the right

# Page 8. Three-Year Financial Projections
- Title: 50 Stores in 3 Years, Revenue Exceeding ¥150M
- Content:
    - Charts:
        - Store count: Year1 8, Year2 25, Year3 50
        - Annual revenue: Year1 ¥18M, Year2 ¥65M, Year3 ¥150M
    - Funding need: ¥5M angel round for first 8 stores
- Design: Dual bar charts (store count + revenue) side by side, funding highlight block at bottom

# Page 9. Ending Page
- Title: Thank You
- SubTitle: Let's put sunshine in every cup, together
- Content:
    - Contact: hello@solcoffee.com
    - WeChat: sol-coffee-official
- Design: Title centered, subtitle below, contact info in small text at bottom, echoing cover page style
```

### Image Format

```markdown
![Image description(width:800,height:600)](https://example.com/image.jpg)
```

Keep the original width, height, and url unchanged.

---

## Design Writing Rules

1. Only describe content area layout; do not include header / footer
2. Do not specify color values (follow the theme)
3. Do not mention theme page IDs
4. Clearly describe spatial relationships of elements (left-right, top-bottom, grid, etc.)

### Layout Diversity

| Content Relevance | Strategy |
|-------------------|----------|
| Highly related (same topic, part 1 & 2) | Keep overall framework consistent, allow local variation |
| Loosely related (different topics) | Vary both framework and details to avoid visual fatigue |

---

## Page Types

### Cover Page (Page 1)

- Required elements: Title, SubTitle
- Clean design, no extra images
- May include date, author

### Table of Contents (Page 2)

- Maximum 8 items; merge into groups if exceeded
- Content should correspond to subsequent chapter sections

### Content Pages

- One topic per page
- Split into multiple pages if content is too dense
- May use Kicker to emphasize key takeaways
- May use Charts / Diagrams to present data

### Ending Page (Last Page)

- Common content: Thank You, Q&A, contact information
- Clean design, echoing cover page style

---

## Notes

1. Do not write layout instructions in Content (layout goes in Design)
2. Content language should match user input
3. Do not repeat the same image across different pages
4. Content pages and ending page should be separate (do not merge)
