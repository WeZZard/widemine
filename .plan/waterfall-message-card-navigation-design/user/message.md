# User / Message

## Fields
| Field | Purpose | Contents | Key | Summary |
|---|---|---|---|---|
| `text` | User-authored message body shown in the navigation preview and card content. | Required string; count 7827; max length 612937; samples include short requests, command wrappers, image markers, long research prompts, and implementation/audit task instructions. | true | true |
| `type` | Raw content subtype marker that confirms the user message is plain text. | Required constant string `text`; count 7827; routes the item to text-message rendering. | true | false |

## Derived Car Form Content
| Field | Source Field | Contents |
|---|---|---|
| Message Text | `text` | Raw user-authored text. |
| Content Type | `type` | `text` |

## Message Navigation Item Design
```text
+--------------------------------------------------------------------------------+
| User / Message                                                    14:32:07      |
| find readycheck-dev/readycheck and readycheck-evals with gh. clone them...      |
+--------------------------------------------------------------------------------+
  category / subtype                                             spacer  time
  summary contents

Preview rules:
- Use the first meaningful line from `text`.
- Preserve user-authored wording; trim only surrounding whitespace and collapse internal line breaks for the one-line preview.
- When `text` starts with structured wrappers such as `<command-name>`, `<bash-input>`, or `<local-command-stdout>`, show the wrapper text as the summary instead of inventing a label.
- Middle-truncate very long content after the first useful segment.
```

## Message Card Design
```text
+------------------------------------------------------------------------------------------------+
| User / Message                                                   14:32:07  [Raw] [Copy JSON]   |
+------------------------------------------------------------------------------------------------+
| Content Form                                                                                   |
|                                                                                                |
|  Message                                                                                       |
|  +------------------------------------------------------------------------------------------+  |
|  | find readycheck-dev/readycheck and readycheck-evals with gh. clone them                   |  |
|  |                                                                                          |  |
|  | Additional paragraphs, command wrappers, image markers, or long task prompts wrap here    |  |
|  | with user-authored wording preserved.                                                     |  |
|  +------------------------------------------------------------------------------------------+  |
|                                                                                                |
|  Text Details                                                                                  |
|  +--------------+---------------------------------------------------------------------------+  |
|  | Content Type | text                                                                      |  |
|  +--------------+---------------------------------------------------------------------------+  |
|                                                                                                |
|  No array fields are present. Raw opens formatted raw JSON for this timeline item; Copy JSON   |
|  copies the raw timeline item from the card action group. Use message typography for `text`    |
|  and smaller balanced monospace only for command-like fragments inside the message body.       |
+------------------------------------------------------------------------------------------------+
```
