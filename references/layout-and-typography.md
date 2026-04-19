# Layout And Typography

These are practical default rules for Chinese formal documents when no organization-issued Word template is provided.
If the user has a real template, that template overrides everything here.

## Page Defaults

- Paper size: A4
- Orientation: portrait unless the content is genuinely tabular
- Margins:
  - `strict-official`: top/bottom `2.54 cm`, left/right `2.8 cm`
  - `formal-business`: top/bottom `2.54 cm`, left/right `2.6 cm`
  - `light-formal`: top/bottom `2.54 cm`, left/right `2.54 cm`

## Font Defaults

Use the most authoritative installed Chinese font available.
When a preferred font is missing, fall back conservatively rather than mixing several decorative fonts.

### `strict-official`

- Title: `方正小标宋简体`, 2号
- Body: `仿宋_GB2312`, 3号
- Level 1 heading: `黑体`, 3号
- Level 2 heading: `楷体_GB2312`, 3号
- Level 3 heading: `仿宋_GB2312`, 3号, bold only if needed

### `formal-business`

- Title: `黑体` or `方正小标宋简体`, 2号
- Body: `仿宋_GB2312` or `宋体`, 3号
- Level 1 heading: `黑体`, 3号
- Level 2 heading: `楷体_GB2312` or `黑体`, 3号
- Tables: `宋体`, 小4 or 5号 depending on density

### `light-formal`

- Title: `黑体`, 2号
- Body: `宋体`, 小4 or 3号
- Headings: `黑体`

## Line And Paragraph Rules

- `strict-official`: fixed line spacing near 28 pt
- `formal-business`: fixed line spacing 26-28 pt or 1.5x if the environment is constrained
- `light-formal`: 1.5x or fixed 24-26 pt
- First line indent: 2 characters for body paragraphs unless a template says otherwise
- Paragraph spacing: keep minimal; formal documents should not look like slide copy

## Heading Hierarchy

Use a stable Chinese heading system.
Pick one hierarchy and keep it through the document.

Common patterns:

- `一、 二、 三、`
- `（一） （二） （三）`
- `1. 2. 3.`
- `（1） （2） （3）`

Avoid mixing several unrelated systems in the same document.

## Tables

- Prefer simple borders and clear headers
- Keep table titles explicit
- Do not use dense color blocks unless a template requires them
- If the table is large, reduce font size before switching to landscape
- Avoid screenshot tables when editable tables are possible

## Page Numbers

- External or formal materials should include page numbers where appropriate
- If the organization already has a footer convention, follow it
- If not specified, use a simple centered or right-aligned footer style

## Fallback Fonts

When the preferred Chinese fonts are unavailable, use the following fallback order:

1. `方正小标宋简体` -> `华文中宋` -> `黑体`
2. `仿宋_GB2312` -> `仿宋` -> `宋体`
3. `楷体_GB2312` -> `楷体` -> `宋体`

Keep the fallback consistent across the whole file.
