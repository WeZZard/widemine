# Detail Popup Content Design - Attachment / Plan File Reference

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Plan Content | `planContent` | Carries the referenced plan body shown by this attachment. | String plan markdown content; observed values can be long and should render fully inside a bounded scroll area. | true |
| Plan File Path | `planFilePath` | Identifies the referenced plan file for the plan body. | String absolute path to the plan file; render as a user-visible path value. | true |
| Type | `type` | Routes the attachment payload shape. | Constant string `plan_file_reference`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Plan Content | `planContent` | Raw `planContent` string from the message JSON. | Complete multiline markdown/text preview with line wrapping and preserved line breaks inside a bounded scroll area; do not add expand/collapse controls. |
| Plan File Path | `planFilePath` | Raw `planFilePath` string from the message JSON. | Monospace copyable path row with middle truncation when constrained. |

## Card Design

```text
+------------------------------------------------------------------------------+
| [Attachment] [Plan File Reference]                                  [pin] [x] |
+------------------------------------------------------------------------------+
|                            Content | Metadata | Raw                           |
+------------------------------------------------------------------------------+
| Plan Content      <planContent multiline preview in bounded scroll area>      |
| Plan File Path    <planFilePath copyable path, middle-truncated if needed>    |
+------------------------------------------------------------------------------+
```
