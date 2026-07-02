# Detail Popup Content Design - Attachment / Hook Success

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Command | `command` | Identifies the hook command that ran successfully. | String command, such as `node "${CLAUDE_PLUGIN_ROOT}/hooks/loop-resume.mjs"` or `${CLAUDE_PLUGIN_ROOT}/hooks/session-start.sh`. | true |
| Content | `content` | Captures any direct attachment body supplied with the hook result. | String; observed as empty in the sampled shapes. | false |
| Duration Ms | `durationMs` | Shows how long the successful hook command took to complete. | Number of milliseconds, with observed values from single-digit runs to multi-second runs. | true |
| Exit Code | `exitCode` | Confirms the successful process result for the hook command. | Number; observed value is `0`. | true |
| Hook Event | `hookEvent` | Identifies the hook event that produced the successful result. | String such as `Stop`, `SessionStart`, `PostToolUseFailure`, or `PostToolUse`. | true |
| Hook Name | `hookName` | Identifies the configured hook name that produced the successful result. | String such as `Stop`, `SessionStart:startup`, `SessionStart:resume`, or `PostToolUse:EnterPlanMode`. | true |
| Stderr | `stderr` | Captures hook stderr diagnostics when emitted. | String; observed as empty in the sampled shapes. | false |
| Stdout | `stdout` | Provides hook stdout that can contain user-facing hook-specific output. | String; observed as `{}` or serialized hook-specific JSON with additional context. | true |
| Stdout JSON | `stdout.$json` | Provides a parsed JSON view of stdout for Metadata and Raw inspection. | Object; present when stdout is JSON. | false |
| Hook Specific Output | `stdout.$json.hookSpecificOutput` | Groups parsed hook-specific output from stdout. | Object containing hook event name and optional additional context. | false |
| Additional Context | `stdout.$json.hookSpecificOutput.additionalContext` | Provides parsed hook-supplied context from stdout JSON. | String containing hook-provided instructions, reminders, diagnostics, or context. | false |
| Hook Event Name | `stdout.$json.hookSpecificOutput.hookEventName` | Provides the hook event name parsed from hook-specific stdout JSON. | String such as `SessionStart`, `PostToolUseFailure`, or `PostToolUse`. | false |
| Tool Use ID | `toolUseID` | Links this hook attachment to related transcript records. | String identifier, including UUID-like ids and `toolu_...` ids. | false |
| Type | `type` | Routes the attachment payload shape; titlebar already communicates category identity. | Constant string `hook_success`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Command | `command` | Use the recorded command string when present; show `Not provided` when absent. | Render in compact monospace with wrapping. |
| Duration Ms | `durationMs` | Use the recorded millisecond number when present; show `Not provided` when absent. | Render as a compact numeric scalar followed by `ms`. |
| Exit Code | `exitCode` | Use the recorded exit code number when present; show `Not provided` when absent. | Render as a compact numeric scalar. |
| Hook Event | `hookEvent` | Use the recorded hook event string when present; show `Not provided` when absent. | Render as a compact scalar value. |
| Hook Name | `hookName` | Use the recorded hook name string when present; show `Not provided` when absent. | Render as a compact scalar value. |
| Stdout | `stdout` | Use the recorded stdout string; when it contains hook-specific JSON, extract values from the stdout payload instead of repeating the full blob; show `Not provided` for empty output or `{}`. | Render extracted stdout values as nested field/value rows, or wrapped monospace text when the value is not structured. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [Attachment] / [Hook Success]                                  [pin] [x] |
+--------------------------------------------------------------------------+
|                         Content | Metadata | Raw                         |
+--------------------------------------------------------------------------+
| Command       <value from command>                                        |
| Duration Ms   <value from durationMs> ms                                  |
| Exit Code     <value from exitCode>                                       |
| Hook Event    <value from hookEvent>                                      |
| Hook Name     <value from hookName>                                       |
| Stdout        <extracted stdout values or Not provided>                   |
+--------------------------------------------------------------------------+
```
