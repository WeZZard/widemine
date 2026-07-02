# Attachment / Hook Success

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `command` | Hook command executed by the runtime. | Required string; observed in all 467 items; max length 51; samples include `node "${CLAUDE_PLUGIN_ROOT}/hooks/loop-resume.mjs"`, `${CLAUDE_PLUGIN_ROOT}/hooks/session-start.sh`, `${CLAUDE_PLUGIN_ROOT}/hooks/post-tool-error.sh`, and `${CLAUDE_PLUGIN_ROOT}/hooks/post-enter-plan-mode.sh`. | true | false |
| `content` | Hook success content payload. | Required string; observed in all 467 items; empty in sampled records. | false | false |
| `durationMs` | Elapsed hook runtime for the success result. | Required number; observed in all 467 items; samples include `102`, `637`, `1462`, and `2975`. | true | false |
| `exitCode` | Process status code returned by the hook command. | Required number; observed in all 467 items; constant sample `0`. | true | false |
| `hookEvent` | Hook lifecycle event that produced the result. | Required string; observed in all 467 items; max length 18; samples include `Stop`, `SessionStart`, `PostToolUseFailure`, and `PostToolUse`. | true | false |
| `hookName` | Visible hook name, including tool-specific suffixes when present. | Required string; observed in all 467 items; max length 27; samples include `Stop`, `SessionStart:startup`, `SessionStart:resume`, `PostToolUseFailure:WebFetch`, `PostToolUse:EnterPlanMode`, and `PostToolUseFailure:Bash`. | true | true |
| `stderr` | Hook standard error stream. | Required string; observed in all 467 items; empty in sampled records. | false | false |
| `stdout` | Hook standard output stream and raw source for parsed hook-specific output. | Required string; observed in all 467 items; max length 3,741; samples include `{}` and JSON containing `hookSpecificOutput`. | true | false |
| `stdout.$json` | Parsed object from JSON-looking `stdout`. | Required object; observed in all 467 items; either empty or containing `hookSpecificOutput`. | false | false |
| `stdout.$json.hookSpecificOutput` | Parsed hook-specific output object from `stdout`. | Object observed in 207 of 467 items; contains hook event name and optional additional context. | false | false |
| `stdout.$json.hookSpecificOutput.additionalContext` | Parsed human-facing context extracted from `stdout`. | String observed in 207 of 467 items; max length 3,538; samples include skill instructions, error-recovery reminders, and plan-mode notices. | false | false |
| `stdout.$json.hookSpecificOutput.hookEventName` | Parsed hook event name extracted from `stdout`. | String observed in 207 of 467 items; max length 18; samples include `SessionStart`, `PostToolUseFailure`, and `PostToolUse`. | false | false |
| `toolUseID` | Hook or tool-call correlation identifier. | Required string; observed in all 467 items; max length 36; samples include UUID-like IDs and `toolu_...` IDs. | false | false |
| `type` | Attachment subtype discriminator. | Required string; observed in all 467 items; constant sample `hook_success`. | false | false |

## Derived Car Form Content

| Field | Source Field | Contents |
| --- | --- | --- |
| Command | `command` | Hook command string. |
| Duration | `durationMs` | Duration in milliseconds. |
| Exit Code | `exitCode` | Numeric process exit code. |
| Hook Event | `hookEvent` | Hook lifecycle event value. |
| Hook Name | `hookName` | Hook name value. |
| Stdout | `stdout` | Raw standard output string. |

## Message Navigation Item Design

```text
Attachment / Hook Success .............................................. 14:32:07
SessionStart:startup | SessionStart | exit 0 | 637 ms
```

Use the attachment-teal tone and render both category levels as full badges. The first line keeps the category/subtype label on the left and timestamp on the right; the second line starts with `hookName`, then shows `hookEvent`, `exitCode`, and `durationMs` as the compact success summary. Do not use raw `stdout` as the navigation summary; when parsed additional context exists, reserve it for the card body.

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [Hook Success]  14:32:07  agent/path          [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Hook                                                                           |
| +----------------+---------------------------------------------------------+   |
| | Hook Name      | SessionStart:startup                                  |   |
| | Hook Event     | SessionStart                                          |   |
| | Command        | ${CLAUDE_PLUGIN_ROOT}/hooks/session-start.sh          |   |
| | Exit Code      | 0                                                     |   |
| | Duration       | 637 ms                                                |   |
| +----------------+---------------------------------------------------------+   |
|                                                                                |
| Additional Context                                                             |
| +----------------------+---------------------------------------------------+   |
| | Hook Event Name      | SessionStart                                      |   |
| | Additional Context   | # Using Amplify Skills                            |   |
| |                      | <EXTREMELY_IMPORTANT> ...                         |   |
| +----------------------+---------------------------------------------------+   |
|                                                                                |
| Failure                                                                        |
| +----------------+---------------------------------------------------------+   |
| | Stderr         | empty                                                 |   |
| +----------------+---------------------------------------------------------+   |
+--------------------------------------------------------------------------------+
```

The card should parse JSON-looking `stdout` and show `stdout.$json.hookSpecificOutput.additionalContext` in the Additional Context table when present; for the 260 plain `{}` outputs, show a compact empty state in that section. Keep `stdout.$json...` helper fields grouped under Additional Context instead of repeating raw stdout. Show the Failure section only when `stderr` is non-empty or the hook event indicates a failed tool-use hook.
