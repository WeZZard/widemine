# Detail Popup Content Design - Attachment / Plan Mode Reentry

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| planFilePath | `planFilePath` | Identifies the saved plan document that the re-entry attachment points back to. | Required string containing an absolute markdown file path in the local Claude plans directory. | true |
| type | `type` | Routes the attachment payload to the plan-mode re-entry subtype; the popup titlebar already exposes this category. | Required string with the observed constant `plan_mode_reentry`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Plan File Path | `planFilePath` | Direct value from `planFilePath`. | Render as a single full-width form row with the value in monospace, preserving the full path and wrapping at path separators when needed. |

## Card Design

```text
+--------------------------------------------------------------+
| [Attachment] [Plan Mode Reentry]                  [pin] [x]  |
+--------------------------------------------------------------+
|                    Content | Metadata | Raw                  |
+--------------------------------------------------------------+
| Plan File Path                                               |
| /Users/wezzard/.claude/plans/example-plan.md                  |
+--------------------------------------------------------------+
```
