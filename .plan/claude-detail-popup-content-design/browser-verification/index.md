# Browser Verification

Portfolio wall verification ran against `http://127.0.0.1:8877/portfolio` at a `5120 x 2880` viewport.

## Coverage

- Unique subtype cards: 53.
- Total portfolio card DOM nodes: 212.
- Visible card checks: 212.
- Type tab checks: 56.
- Tab switch checks: 221.
- Surfaces checked:
  - Timeline / Block: 53 unique cards.
  - Timeline / Detailed Message Popup: 53 unique cards.
  - Waterfall / Message Card: 53 unique cards.
  - Waterfall / Message Navigation Item: 53 unique cards.

## Result

- Badge visual mismatches: 0.
- Detail popup structure issues: 0.
- Overflow issues: 0.
- Interaction failures: 0.
- Errors: 0.

## Screenshots

- `portfolio-surface-timeline-block-5120x2880.png`
- `portfolio-surface-timeline-detail-5120x2880.png`
- `portfolio-surface-waterfall-card-5120x2880.png`
- `portfolio-surface-waterfall-navigation-5120x2880.png`
- `portfolio-wall-final-5120x2880.png`

## 2026-06-22 Detail Popup Fix Check

Ran against `http://127.0.0.1:8878` at a `5120 x 2880` viewport.

- Portfolio detail popup pin and close buttons resolve to one size: `30 x 30`.
- Single-card detailed popup specimen groups render with fixed `540px` cards instead of stretching to the available row width.
- Portfolio table/list headers remain sticky at the same top offset after scrolling to the bottom and back.
- Portfolio detail cards show list counts such as `154 items`; no `+N more` text or field expand buttons remain.
- Portfolio raw payload specimens contain no `__truncated__` or sampled `more items` markers.
- Real conversation detail popup uses `base.css?v=20260622-detail-panel-v6` and `conversation.js?v=20260622-detail-panel-v6`.
- Real conversation detail popup pin and close buttons resolve to one size: `30 x 30`.
- Real conversation attachment/system sections contain no `+N more` text and no `Expand` or `Collapse` section buttons.
- Real conversation raw panel renders formatted JSON without sampler truncation.

Screenshot:

- `session-viewer-detail-popup-fixes-5120x2880.png`

## 2026-06-22 Full List Detail Popup Check

Ran against `http://127.0.0.1:8880` at a `5120 x 2880` viewport.

- Portfolio `system / compact boundary` detailed popup loads every list item directly:
  - `Pre Compact Discovered Tools`: `4 items`, 4 rendered rows.
  - `All UUIDs`: `363 items`, 363 rendered rows.
  - `UUIDs`: `355 items`, 355 rendered rows.
- Real conversation `system / compact boundary` detailed popup loads every list item directly:
  - `Pre-Compact Tools`: `18 items`, 18 rendered list items.
  - `All UUIDs`: `238 items`, 238 rendered list items.
  - `UUIDs`: `225 items`, 225 rendered list items.
- No `+N more` text, sampled `... N more items` text, or `Expand`/`Collapse` list buttons were present in the checked detail popup cards.
- Real conversation Raw panel contained no `__truncated__` or sampled `more items` markers.

Screenshot:

- `detail-popup-full-list-compact-boundary-5120x2880.png`

## 2026-06-22 Newline Preservation and Table Order Check

Ran against `http://127.0.0.1:8881` at a `5120 x 2880` viewport.

- Portfolio `attachment / invoked skills` detailed popup renders the `Skills` table with headers `Name`, `Content`; the first content cell contains source newline characters and computes to `white-space: pre-wrap`.
- Portfolio `attachment / hook additional context` detailed popup renders the `Content` table with newline-bearing text and `white-space: pre-wrap`.
- Portfolio `attachment / MCP instructions delta` detailed popup renders the `Added Blocks` table with newline-bearing text and `white-space: pre-wrap`.
- Portfolio visible attachment detail tables had no data-row mismatches between generated `contentBlocks` and rendered table rows.
- Live conversation `attachment / invoked skills` detailed popup renders `Name`, `Content` in that order, with 3 skill rows and newline-preserving `pre-wrap` table cells.
- Live conversation `attachment / hook additional context` detailed popup renders the text section as a `pre` with source newlines preserved and `white-space: pre-wrap`.
- Live conversation `attachment / MCP instructions delta` detailed popup renders instruction block list items with source newlines preserved and `white-space: pre-wrap`.
- Checked detail panels contained no `Expand`, `Collapse`, or `+N more` text.

Screenshot:

- `newline-preservation-5120x2880.png`
