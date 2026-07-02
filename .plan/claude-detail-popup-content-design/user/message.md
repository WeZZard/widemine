# Detail Popup Content Design - User / Message

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Text | `text` | Carries the user-authored natural-language message shown in the Content section. | Required string; observed in 7,546 messages; max observed length 612,937 characters. | true |
| Type | `type` | Routes the text content block shape and is already represented by the popup category badges. | Required string; observed value is `text`; max observed length 4 characters. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Text | `text` | Read directly from the message JSON object's `text` field. | Render as selectable multiline message text; preserve line breaks and wrapping, with expansion for very long content. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [User] [Message]                                               [pin] [x] |
+--------------------------------------------------------------------------+
|                         Content | Metadata | Raw                         |
+--------------------------------------------------------------------------+
| Text                                                                     |
| <selectable multiline value from text>                                   |
+--------------------------------------------------------------------------+
```
