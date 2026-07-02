# Detail Popup Content Design - Attachment / Plan Mode

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Is Sub Agent | `isSubAgent` | Records whether the attachment was emitted from a subagent context. | Boolean value observed as `false`. | false |
| Plan Exists | `planExists` | Indicates whether the current plan-mode state has a backing plan file. | Boolean value observed as `true` or `false`. | true |
| Plan File Path | `planFilePath` | Provides the file location for the plan associated with the plan-mode state. | Absolute markdown path in the Claude plans directory. | true |
| Reminder Type | `reminderType` | Describes which plan-mode reminder variant is active. | String value observed as `full` or `sparse`. | true |
| Type | `type` | Routes the attachment subtype already represented by the titlebar badges. | Constant string value `plan_mode`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Plan Exists | `planExists` | Direct value from `planExists`. | Render as a boolean status value. |
| Plan File Path | `planFilePath` | Direct value from `planFilePath`. | Render as a copyable path with middle truncation when space is constrained. |
| Reminder Type | `reminderType` | Direct value from `reminderType`. | Render as a compact scalar text value. |

## Card Design

```text
+------------------------------------------------------------------------+
| [Attachment] [Plan Mode]                                      [pin] [x] |
+------------------------------------------------------------------------+
|                         Content | Metadata | Raw                       |
+------------------------------------------------------------------------+
| Plan Exists       true                                                 |
| Plan File Path    /Users/wezzard/.claude/plans/example-plan.md         |
| Reminder Type     full                                                 |
+------------------------------------------------------------------------+
```
