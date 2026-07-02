# Detail Popup Content Design - Attachment / Ultra Effort Enter

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Reminder Type | `reminderType` | Captures the reminder variant emitted when ultra effort mode is entered. | Required string; observed values include `full` and `sparse`. | true |
| Type | `type` | Routes the attachment subtype already represented by the popup badges. | Required string; observed value is `ultra_effort_enter`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Reminder Type | `reminderType` | Read directly from `reminderType`. | Render as a compact scalar text row; show `Not provided` only if the field is absent. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [Attachment] [Ultra Effort Enter]                              [pin] [x] |
+--------------------------------------------------------------------------+
|                         Content | Metadata | Raw                         |
+--------------------------------------------------------------------------+
| Reminder Type                                           <reminderType>   |
+--------------------------------------------------------------------------+
```
