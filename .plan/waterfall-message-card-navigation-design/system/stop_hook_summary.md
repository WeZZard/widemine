# System / Stop Hook Summary

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `cwd` | Working directory context for the stop-hook event. | Required string; observed 1,374; max length 135. | false | false |
| `entrypoint` | Client entrypoint that produced the event. | Required string; observed 1,374; max length 13; samples include `cli` and `claude-vscode`. | false | false |
| `gitBranch` | Repository branch context for the event. | Required string; observed 1,374; max length 43. | false | false |
| `hasOutput` | Indicates whether stop-hook processing emitted output. | Required bool; observed 1,374; samples include `false` and `true`. | true | false |
| `hookAdditionalContext` | Additional context array and count source. | Optional array; observed 1,108; max 1 item. | true | false |
| `hookAdditionalContext[]` | Hook-provided additional context text. | Optional string item; observed 1; max length 751. | true | false |
| `hookCount` | Number of stop hooks evaluated. | Required number; observed 1,374; samples include `1`, `2`, and `3`. | true | true |
| `hookErrors` | Hook error array and count source. | Required array; observed 1,374; max 1 item. | true | false |
| `hookErrors[]` | Hook error or loop-status text. | Optional string item; observed 14; max length 101. | true | false |
| `hookInfos` | Hook run record array and count source. | Required array; observed 1,374; max 3 items. | true | false |
| `hookInfos[]` | Container for one hook run record. | Optional object item; observed 2,577. | false | false |
| `hookInfos[].command` | Command executed for a hook run. | Optional string; observed 2,577; max length 265; samples include `node "${CLAUDE_PLUGIN_ROOT}/scripts/stop-review-gate-hook.mjs"` and `node "${CLAUDE_PLUGIN_ROOT}/hooks/loop-resume.mjs"`. | true | false |
| `hookInfos[].durationMs` | Hook run duration in milliseconds. | Optional number; observed 2,576. | true | false |
| `hookInfos[].promptText` | Prompt text attached to a hook run when present. | Optional string; observed 1; max length 265. | true | false |
| `isSidechain` | Sidechain routing marker for the event. | Required bool; observed 1,374; constant sample `false`. | false | false |
| `level` | Stop hook summary severity level. | Required string; observed 1,374; max length 10; constant sample `suggestion`. | true | false |
| `parentUuid` | Parent transcript record identifier. | Required string; observed 1,374; max length 36. | false | false |
| `preventedContinuation` | Indicates whether hook processing prevented continuation. | Required bool; observed 1,374; constant sample `false`. | true | false |
| `sessionId` | Transcript session identifier. | Required string; observed 1,374; max length 36. | false | false |
| `slug` | Scan or session slug metadata when present. | Optional string; observed 1,006; max length 53. | false | false |
| `stopReason` | Stop reason attached to the hook summary. | Required string; observed 1,374; blank in extracted samples. | true | false |
| `subtype` | Raw subtype discriminator for routing. | Required string; observed 1,374; constant sample `stop_hook_summary`. | false | false |
| `timestamp` | Event time for sorting and display. | Required string; observed 1,374; max length 24. | false | false |
| `toolUseID` | Hook or tool-use correlation identifier. | Required string; observed 1,374; max length 36. | false | false |
| `type` | Raw type discriminator for routing. | Required string; observed 1,374; constant sample `system`. | false | false |
| `userType` | Transcript user category metadata. | Required string; observed 1,374; max length 8; constant sample `external`. | false | false |
| `uuid` | Transcript record identifier. | Required string; observed 1,374; max length 36. | false | false |
| `version` | Producer version metadata. | Required string; observed 1,374; max length 7. | false | false |

## Derived Car Form Content

| Field | Source Field | Contents |
| --- | --- | --- |
| Has Output | `hasOutput` | Raw boolean value. |
| Hook Additional Context | `hookAdditionalContext` | Raw array value. |
| Hook Additional Context Item | `hookAdditionalContext[]` | Raw string item. |
| Hook Count | `hookCount` | Raw number value. |
| Hook Errors | `hookErrors` | Raw array value. |
| Hook Error Item | `hookErrors[]` | Raw string item. |
| Hook Infos | `hookInfos` | Raw array value. |
| Hook Command | `hookInfos[].command` | Raw string value for each hook run record. |
| Hook Duration Ms | `hookInfos[].durationMs` | Raw number value for each hook run record. |
| Hook Prompt Text | `hookInfos[].promptText` | Raw string value for each hook run record when present. |
| Level | `level` | Raw string value. |
| Prevented Continuation | `preventedContinuation` | Raw boolean value. |
| Stop Reason | `stopReason` | Raw string value. |

## Message Navigation Item Design

```text
+--------------------------------------------------------------------------------+
| System / Stop Hook Summary ......................................... 13:44:57 |
| 3 hooks | output=true | prevented=false | errors=1 | node "${CLAUDE_PLUGIN... |
+--------------------------------------------------------------------------------+
```

Line 1 is the category/subtype label, flexible spacer, and timestamp. Line 2 is the summary contents: prefer the first non-empty `hookAdditionalContext[]`, then the first `hookErrors[]`, then `hookCount` with `hasOutput`, `preventedContinuation`, and the first `hookInfos[].command`. Keep `System` and `Stop Hook Summary` as full badges in the rendered navigation item, and use error emphasis only when `hookErrors[]` is present.

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [System] [Stop Hook Summary]  13:44:57  agent/path        [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Stop Hook Outcome                                                              |
| +------------------------+---------------------------------------------------+ |
| | Hook Count             | 3                                                 | |
| | Has Output             | true                                              | |
| | Prevented Continuation | false                                             | |
| | Level                  | suggestion                                        | |
| | Stop Reason            |                                                   | |
| +------------------------+---------------------------------------------------+ |
|                                                                                |
| Hook Additional Context                                                        |
| +-----+--------------------------------------------------------------------+  |
| | #   | hookAdditionalContext[]                                            |  |
| +-----+--------------------------------------------------------------------+  |
| | 1   | <EXTREMELY_IMPORTANT> The amplify:execute-plan scheduling loop... |  |
| +-----+--------------------------------------------------------------------+  |
|                                                                                |
| Hook Errors                                                                    |
| +-----+--------------------------------------------------------------------+  |
| | #   | hookErrors[]                                                       |  |
| +-----+--------------------------------------------------------------------+  |
| | 1   | amplify:execute-plan loop has ready work but no subagents...      |  |
| +-----+--------------------------------------------------------------------+  |
|                                                                                |
| Hook Infos                                                                     |
| +-----+---------------------------------------------+-------------+--------+ |
| | #   | hookInfos[].command                         | durationMs  | prompt | |
| +-----+---------------------------------------------+-------------+--------+ |
| | 1   | node "${CLAUDE_PLUGIN_ROOT}/scripts/..."    | 89          |        | |
| | 2   | node "${CLAUDE_PLUGIN_ROOT}/hooks/..."      | 1015        | text   | |
| +-----+---------------------------------------------+-------------+--------+ |
+--------------------------------------------------------------------------------+
```

The card body is one content form. Render scalar outcome fields first, then group the flattened array fields into nested tables: `hookAdditionalContext[]` under `hookAdditionalContext`, `hookErrors[]` under `hookErrors`, and `hookInfos[].command`, `hookInfos[].durationMs`, and `hookInfos[].promptText` under `hookInfos[]`. Empty arrays stay visible as empty nested tables so a zero-error or zero-context stop summary is distinguishable from missing data.
