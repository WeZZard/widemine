# Detail Popup Content Design - Mode / Raw Event

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| mode | `mode` | Carries the mode state reported by this raw event. | String scalar; observed sample `normal`; present on all 2806 observed records. | true |
| sessionId | `sessionId` | Identifies the transcript session for routing and traceability; keep in Metadata. | UUID string; present on all 2806 observed records. | false |
| type | `type` | Provides the first-level message category already shown in the popup titlebar. | Constant string `mode`; present on all 2806 observed records. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Mode | `mode` | Raw `mode` scalar from the message JSON. | Render as one read-only scalar row. |

## Card Design

```text
+------------------------------------------------------------------+
| [Mode] [Raw Event]                                      [pin] [x] |
+------------------------------------------------------------------+
|                     Content | Metadata | Raw                     |
+------------------------------------------------------------------+
| Mode                                                     normal   |
+------------------------------------------------------------------+
```
