# Attachment / Hook Non Blocking Error

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `command` | Hook command executed by the runtime. | Required string; observed in all 13 items; max length 62; sample `node "${CLAUDE_PLUGIN_ROOT}/scripts/stop-review-gate-hook.mjs"`. | true | false |
| `durationMs` | Elapsed hook runtime for the non-blocking error result. | Required number; observed in all 13 items; samples include `10`, `7`, `5`, and `8`. | true | false |
| `exitCode` | Process status code returned by the hook command. | Required number; observed in all 13 items; constant sample `127`. | true | false |
| `hookEvent` | Hook lifecycle event that produced the result. | Required string; observed in all 13 items; max length 4; sample `Stop`. | true | false |
| `hookName` | Visible hook name. | Required string; observed in all 13 items; max length 4; sample `Stop`. | true | false |
| `stderr` | Hook standard error stream and concise failure detail. | Required string; observed in all 13 items; max length 70; sample `Failed with non-blocking status code: /bin/sh: node: command not found`. | true | true |
| `stdout` | Hook standard output stream and possible source for parsed hook-specific context. | Required string; observed in all 13 items; no non-empty samples reported. | true | false |
| `toolUseID` | Hook or tool-call correlation identifier. | Required string; observed in all 13 items; max length 36; samples include UUID-like IDs. | false | false |
| `type` | Attachment subtype discriminator. | Required string; observed in all 13 items; constant sample `hook_non_blocking_error`. | false | false |

## Derived Car Form Content

| Field | Source Field | Contents |
| --- | --- | --- |
| Command | `command` | Hook command string. |
| Duration | `durationMs` | Duration in milliseconds. |
| Exit Code | `exitCode` | Numeric process exit code. |
| Hook Event | `hookEvent` | Hook lifecycle event value. |
| Hook Name | `hookName` | Hook name value. |
| Stderr | `stderr` | Standard error string. |
| Stdout | `stdout` | Standard output string. |

## Message Navigation Item Design

```text
Attachment / Hook Non Blocking Error ................................. 14:32:07
Stop | Stop | exit 127 | Failed with non-blocking status code: /bin/sh: node: command not found
```

Use the attachment-teal tone and render both category levels as full badges. The first line keeps the category/subtype label on the left and timestamp on the right; the second line starts with `hookName`, then shows `hookEvent`, `exitCode`, and the single-line `stderr` summary. Keep the preview clipped to one line so the non-blocking failure is visible without expanding the card.

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [Hook Non Blocking Error]  14:32:07  agent/path                |
|                                                              [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Hook                                                                           |
| +----------------+---------------------------------------------------------+   |
| | Hook Name      | Stop                                                    |   |
| | Hook Event     | Stop                                                    |   |
| | Command        | node "${CLAUDE_PLUGIN_ROOT}/scripts/stop-review-gate-   |   |
| |                | hook.mjs"                                               |   |
| | Exit Code      | 127                                                     |   |
| | Duration       | 10 ms                                                   |   |
| +----------------+---------------------------------------------------------+   |
|                                                                                |
| Additional Context                                                             |
| +----------------+---------------------------------------------------------+   |
| | Parsed Context | empty                                                   |   |
| +----------------+---------------------------------------------------------+   |
|                                                                                |
| Failure                                                                        |
| +----------------+---------------------------------------------------------+   |
| | Blocking       | non-blocking                                            |   |
| | Stderr         | Failed with non-blocking status code: /bin/sh: node:    |   |
| |                | command not found                                      |   |
| +----------------+---------------------------------------------------------+   |
+--------------------------------------------------------------------------------+
```

The card should parse JSON-looking `stdout` and show extracted `hookSpecificOutput` context in Additional Context when present; do not repeat raw `stdout`. For the observed empty `stdout` values, render the compact empty state shown above. Keep the Failure section visible for this subtype, with `stderr` as the primary human-facing detail and the non-blocking status presented as the failure mode. Raw opens formatted raw JSON for the timeline item, and Copy JSON copies the raw payload.
