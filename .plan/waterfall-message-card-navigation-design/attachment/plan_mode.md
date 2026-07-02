# Attachment / Plan Mode

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `type` | Identifies the attachment subtype for routing and category badges. | Constant string `plan_mode`. | false | false |
| `isSubAgent` | Records whether the plan-mode attachment was emitted from a subagent context. | Boolean value observed as `false`. | false | false |
| `planExists` | Indicates whether the referenced plan file exists. | Boolean value observed as `true` or `false`. | true | false |
| `planFilePath` | Provides the markdown file path associated with the plan-mode state. | Absolute path in the Claude plans directory. | true | true |
| `reminderType` | Records which plan-mode reminder variant is active. | String value observed as `full` or `sparse`. | true | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Plan Exists | Boolean value from `planExists`. |
| Plan File Path | Absolute path from `planFilePath`. |
| Reminder Type | String value from `reminderType`. |

## Message Navigation Item Design

```text
Attachment / Plan Mode ................................................ 13:09:44
/Users/wezzard/.claude/plans/{plan-file}.md
```

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| o  Attachment / Plan Mode  main ..................................... 13:09:44 |
|                                                         [Raw] [Copy JSON]      |
+--------------------------------------------------------------------------------+
| Plan Mode                                                                      |
|                                                                                |
| +----------------+-----------------------------------------------------------+ |
| | Field          | Value                                                     | |
| +----------------+-----------------------------------------------------------+ |
| | Plan Exists    | false                                                     | |
| | Plan File Path | /Users/wezzard/.claude/plans/{plan-file}.md              | |
| | Reminder Type  | full                                                      | |
| +----------------+-----------------------------------------------------------+ |
+--------------------------------------------------------------------------------+
```
