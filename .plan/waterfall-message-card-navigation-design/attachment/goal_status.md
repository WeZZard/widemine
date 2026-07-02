# Attachment / Goal Status

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `condition` | Goal condition text used as the primary status target and preview line. | Required string; observed in all 3 items across 2 shapes; max length 272; sample begins `Let's review the test cases: 1. Run the test cases, but do not fix them if they break...`. | true | true |
| `met` | Goal result status. | Required boolean; observed in all 3 items; samples include `false` for sentinel records and `true` for the completed result. | true | false |
| `reason` | Completion rationale for a met goal. | Required string in the completed-result shape; observed in 1 item; max length 489; sample begins `All 220 tests passed with 0 failed (4 intentionally ignored)...`. | true | false |
| `durationMs` | Duration value attached to a completed goal status. | Required number in the completed-result shape; observed in 1 item; sampled value is `62528`. | true | false |
| `iterations` | Iteration count attached to a completed goal status. | Required number in the completed-result shape; observed in 1 item; sampled value is `1`. | true | false |
| `tokens` | Token count attached to a completed goal status. | Required number in the completed-result shape; observed in 1 item; sampled value is `439`. | true | false |
| `sentinel` | Sentinel marker on the non-completed goal-status shape. | Required boolean in the sentinel shape; observed in 2 items; sampled value is `true`. | false | false |
| `type` | Attachment subtype discriminator. | Required constant string `goal_status`. | false | false |

## Derived Car Form Content

| Field | Source Field | Contents |
| --- | --- | --- |
| Condition | `condition` | Value from `condition`. |
| Met | `met` | Value from `met`. |
| Reason | `reason` | Value from `reason` when present. |
| Duration Ms | `durationMs` | Value from `durationMs` when present. |
| Iterations | `iterations` | Value from `iterations` when present. |
| Tokens | `tokens` | Value from `tokens` when present. |

## Message Navigation Item Design

```text
Attachment / Goal Status ............................................. 06:03:04
Let's review the test cases: 1. Run the test cases, but do not fix them...
```

Use the attachment-teal tone and render both category levels as full badges. The first line keeps `Attachment / Goal Status` on the left and right-aligns the timestamp. The second line is the whitespace-collapsed `condition` value, truncated only for available width.

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Attachment / Goal Status ............................................ 06:03:04 |
| agent/path                                                [Raw] [Copy JSON]    |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Goal Status                                                                    |
| +-------------+------------------------------------------------------------+   |
| | Field       | Value                                                      |   |
| +-------------+------------------------------------------------------------+   |
| | Condition   | Let's review the test cases:                              |   |
| |             | 1. Run the test cases, but do not fix them if they break. |   |
| |             | 2. Review whether failed assertions are correctly...      |   |
| | Met         | true                                                       |   |
| | Reason      | All 220 tests passed with 0 failed (4 intentionally...    |   |
| +-------------+------------------------------------------------------------+   |
|                                                                                |
| Completion Fields                                                              |
| +-------------+------------------------------------------------------------+   |
| | Field       | Value                                                      |   |
| +-------------+------------------------------------------------------------+   |
| | Duration Ms | 62528                                                      |   |
| | Iterations  | 1                                                          |   |
| | Tokens      | 439                                                        |   |
| +-------------+------------------------------------------------------------+   |
|                                                                                |
| Raw button opens formatted raw JSON for this timeline item.                    |
| Copy JSON copies the raw payload.                                              |
+--------------------------------------------------------------------------------+
```

No nested array table is needed because all observed fields are flat. For sentinel-shape records, show the `Condition` and `Met` rows and omit the completion-only `Reason`, `Duration Ms`, `Iterations`, and `Tokens` rows when those fields are absent.
