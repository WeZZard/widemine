# Assistant / Reasoning

## Fields
| Field | Purpose | Contents | Key | Summary |
|---|---|---|---|---|
| `signature` | Opaque reasoning signature kept for raw inspection and metadata support. | Required string; count 6259; max length 59648; not shown in normal content. | false | false |
| `thinking` | Assistant reasoning text shown in the navigation preview and primary card content. | Required string; count 6259; max length 14247; preserve long text with in-place expansion. | true | true |
| `type` | Content subtype discriminator that routes this item to the Reasoning surface. | Required constant string `thinking`; count 6259. | true | false |

## Derived Car Form Content
| Field | Source Field | Contents |
|---|---|---|
| Reasoning | `thinking` | Raw assistant reasoning text. |
| Content Type | `type` | `thinking` |

## Message Navigation Item Design
```text
Assistant / Reasoning                                             14:32:07
I need to clone two GitHub repositories from the `readycheck-dev`...

category / subtype                                             spacer  time
summary contents

Preview rules:
- Use the first meaningful line from `thinking`.
- Keep the Assistant and Reasoning labels as full category badges in the actual UI.
- Preserve inline code cues while trimming the preview to one row.
- Do not use `signature` for the preview.
```

## Message Card Design
```text
+------------------------------------------------------------------------------------------------+
| Assistant / Reasoning                                            14:32:07  [Raw] [Copy JSON]   |
+------------------------------------------------------------------------------------------------+
| Content Form                                                                                   |
|                                                                                                |
|  Reasoning                                                                                     |
|  +------------------------------------------------------------------------------------------+  |
|  | I need to clone two GitHub repositories from the `readycheck-dev` organization using      |  |
|  | the `gh` CLI tool and place them in the standard artifact directory structure...          |  |
|  |                                                                                          |  |
|  | Additional reasoning text wraps here with transcript typography. Long content expands     |  |
|  | in place instead of moving to a separate view.                                             |  |
|  +------------------------------------------------------------------------------------------+  |
|                                                                                                |
|  Details                                                                                       |
|  +--------------+---------------------------------------------------------------------------+  |
|  | Content Type | thinking                                                                  |  |
|  +--------------+---------------------------------------------------------------------------+  |
|                                                                                                |
|  No array fields are present. Keep `signature` out of the content form; Raw opens formatted    |
|  raw JSON for this timeline item, and Copy JSON copies the raw payload including `signature`.  |
|  Use assistant-blue tone and smaller balanced monospace only for command-like fragments.       |
+------------------------------------------------------------------------------------------------+
```
