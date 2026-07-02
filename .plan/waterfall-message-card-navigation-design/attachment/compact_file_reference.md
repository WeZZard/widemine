# Attachment / Compact File Reference Waterfall Surface Design

## Fields
| Field | Purpose | Contents | Key | Summary |
|---|---|---|---|---|
| `displayPath` | Compact file path for row and card scanning. | Required string; count 8; max length 43; samples include `claude/amplify/scripts/task.test.mjs` and `../../../../tmp/rbx-whiteboard-graph.json`. | true | true |
| `filename` | Absolute file path for the referenced file. | Required string; count 8; max length 107; samples include repo paths and `/tmp/rbx-whiteboard-graph.json`. | true | false |
| `type` | Raw attachment subtype discriminator. | Required string; count 8; constant sample `compact_file_reference`. | true | false |

## Derived Car Form Content
| Field | Purpose | Contents |
|---|---|---|
| Display Path | Compact file path. | `displayPath` |
| Filename | Absolute file path. | `filename` |
| Type | Attachment subtype marker. | `compact_file_reference` |

## Message Navigation Item Design
```text
+--------------------------------------------------------------------------------+
| o  [Attachment] [Compact File Reference]  14:32  claude/amplify/.../task.mjs   |
+--------------------------------------------------------------------------------+
  activity dot   full badges                    timestamp  one-line preview
  tone: attachment-teal; use the same full badge style for both badges

Preview rules:
- Use `displayPath` as the first meaningful content line.
- Fall back to `filename` when `displayPath` is unavailable.
- Keep the path one line, middle-truncated when needed.
```

## Message Card Design
```text
Attachment-teal waterfall message card

Title bar
+------------------------------------------------------------------------------------------------+
| o  [Attachment] [Compact File Reference]  14:32:07  agent/path                [Raw] [Copy JSON] |
+------------------------------------------------------------------------------------------------+

Content form
+------------------------------------------------------------------------------------------------+
| File Reference                                                                                 |
| +--------------+-----------------------------------------------------------------------------+ |
| | Display Path | claude/amplify/scripts/task.test.mjs                                         | |
| | Filename     | /Users/wezzard/Artifacts/Repositories/.../claude/amplify/scripts/task.mjs   | |
| | Type         | compact_file_reference                                                      | |
| +--------------+-----------------------------------------------------------------------------+ |
|                                                                                                |
| Path Preview                                                                                   |
| +--------------------------------------------------------------------------------------------+ |
| | claude/amplify/scripts/task.test.mjs                                                        | |
| +--------------------------------------------------------------------------------------------+ |
+------------------------------------------------------------------------------------------------+

No array fields are present. Raw opens formatted raw JSON for this timeline item; Copy JSON copies
the raw timeline item.
```
