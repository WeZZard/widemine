# Detail Popup Content Design - Attachment / Hook Non Blocking Error

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Command | `command` | Shows the hook command that ran and anchors the failure to the executed script. | String; sample `node "${CLAUDE_PLUGIN_ROOT}/scripts/stop-review-gate-hook.mjs"`. | true |
| Duration Ms | `durationMs` | Supports the hook run result with elapsed execution time. | Number; samples `10`, `7`, `5`, `8`. | true |
| Exit Code | `exitCode` | Shows the process result code returned by the failed non-blocking hook. | Number; sample `127`. | true |
| Hook Event | `hookEvent` | Identifies the hook event that produced the non-blocking error. | String; sample `Stop`. | true |
| Hook Name | `hookName` | Identifies the configured hook name that produced the non-blocking error. | String; sample `Stop`. | true |
| Stderr | `stderr` | Shows the failure detail emitted for the non-blocking hook error. | String; sample `Failed with non-blocking status code: /bin/sh: node: command not found`. | true |
| Stdout | `stdout` | Provides hook output that can contain user-facing hook-specific context. | String; observed as empty in the sample; JSON-looking values may include hook-specific output. | true |
| Tool Use ID | `toolUseID` | Correlates this attachment with tool-use records and transcript tracing. | String; UUID-like values such as `f5610fd3-9a93-438c-9482-3d49c47f1744`. | false |
| Type | `type` | Routes the raw attachment subtype; category identity belongs to the popup titlebar. | String; sample `hook_non_blocking_error`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Command | `command` | Use the recorded command value when present; show `Not provided` when absent. | Render in compact monospace with wrapping and no clipping. |
| Duration Ms | `durationMs` | Use the recorded duration value when present; show `Not provided` when absent. | Render as a numeric scalar followed by `ms`. |
| Exit Code | `exitCode` | Use the recorded exit code value when present; show `Not provided` when absent. | Render as a plain numeric scalar. |
| Hook Event | `hookEvent` | Use the recorded hook event value when present; show `Not provided` when absent. | Render as a plain text scalar. |
| Hook Name | `hookName` | Use the recorded hook name value when present; show `Not provided` when absent. | Render as a plain text scalar. |
| Stderr | `stderr` | Use the recorded stderr value when present; show `Not provided` when absent. | Render as wrapped diagnostic text, preserving meaningful line breaks. |
| Stdout | `stdout` | Use the recorded stdout value; when it contains JSON, extract hook-specific output values instead of repeating the full stdout blob; show `Not provided` when empty. | Render extracted values as nested field/value rows, or wrapped text when the value is not structured. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [Attachment] [Hook Non Blocking Error]                         [pin] [x] |
+--------------------------------------------------------------------------+
|                         Content | Metadata | Raw                         |
+--------------------------------------------------------------------------+
| Command       <value from command>                                        |
| Duration Ms   <value from durationMs> ms                                  |
| Exit Code     <value from exitCode>                                       |
| Hook Event    <value from hookEvent>                                      |
| Hook Name     <value from hookName>                                       |
| Stderr        <value from stderr>                                         |
| Stdout        <extracted values from stdout or Not provided>              |
+--------------------------------------------------------------------------+
```
