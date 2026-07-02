# Detail Popup Content Design - Assistant / Reasoning

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Signature | `signature` | Verification payload for assistant reasoning, retained for audit and raw inspection. | Required string in every observed message; long encoded signature. Keep out of Content. | false |
| Thinking | `thinking` | Main reasoning text emitted for this assistant item. | Required string in every observed message; long-form reasoning text with possible line breaks. | true |
| Type | `type` | Inner content discriminator already represented by the popup's second-level badge. | Required string; observed value `thinking`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Thinking | `thinking` | Direct message JSON value at `thinking`. | Render as a long-text field with preserved whitespace and line breaks inside a bounded scroll area; do not add expand/collapse controls. |

## Card Design

```text
+------------------------------------------------------------------------------+
| [Assistant] [Reasoning]                                           [pin] [x]   |
+------------------------------------------------------------------------------+
|                             Content | Metadata | Raw                          |
+------------------------------------------------------------------------------+
| Thinking                                                                       |
| <thinking text, preserving whitespace and line breaks>                         |
| <continues in scroll area with preserved line breaks>                         |
+------------------------------------------------------------------------------+
```
