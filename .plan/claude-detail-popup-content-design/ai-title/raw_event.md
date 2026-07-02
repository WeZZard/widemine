# Detail Popup Content Design - AI Title / Raw Event

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| AI Title | `aiTitle` | Shows the generated title for the session. | String title text; examples include `Clone readycheck repositories locally`. | true |
| Session ID | `sessionId` | Identifies the transcript session that emitted the event. | UUID string. | false |
| Type | `type` | Routes the raw event into its timeline category. | Constant string `ai-title`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| AI Title | `aiTitle` | Use the recorded `aiTitle` string. | Render as a single wrapped text value. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [AI Title] [Raw Event]                                          [pin] [x] |
+--------------------------------------------------------------------------+
|                         Content | Metadata | Raw                         |
+--------------------------------------------------------------------------+
| <aiTitle value, wrapped as plain text>                                    |
+--------------------------------------------------------------------------+
```
