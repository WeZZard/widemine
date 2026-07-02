# Detail Popup Content Design - Attachment / Plan Mode Exit

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Plan Exists | `planExists` | Shows whether plan mode exited with an existing plan file. | Boolean value observed as `true` or `false`. | true |
| Plan File Path | `planFilePath` | Identifies the plan file associated with the plan mode exit. | Absolute markdown path under the Claude plans directory. | true |
| Type | `type` | Routes the attachment payload to the plan mode exit renderer. | Constant string value `plan_mode_exit`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Plan Exists | `planExists` | Read the boolean value directly from `planExists`. | Render as a scalar boolean value. |
| Plan File Path | `planFilePath` | Read the string value directly from `planFilePath`. | Render as a copyable file path with middle truncation when space is constrained. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [Attachment] [Plan Mode Exit]                                  [pin] [x] |
+--------------------------------------------------------------------------+
|                         Content | Metadata | Raw                         |
+--------------------------------------------------------------------------+
| Plan Exists      <planExists>                                            |
| Plan File Path   <planFilePath>                                          |
+--------------------------------------------------------------------------+
```
