# Detail Popup Content Design - Attachment / Date Change

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| New Date | `newDate` | Provides the date boundary introduced by this attachment. | Date string in `YYYY-MM-DD` form. | true |
| Type | `type` | Routes the attachment to the date-change renderer. | Constant raw value `date_change`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| New Date | `newDate` | Direct value from `newDate`. | Render as a single date field. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [Attachment] [Date Change]                                    [pin] [x] |
+--------------------------------------------------------------------------+
|                    Content | Metadata | Raw                              |
+--------------------------------------------------------------------------+
| New Date                                             2026-06-14          |
+--------------------------------------------------------------------------+
```
