# Attachment / Hook Blocking Error

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `blockingError` | Container for blocking hook failure details. | Required object; observed in all 1 item; contains `blockingError` and `command`. | true | false |
| `blockingError.blockingError` | Human-facing blocking failure message. | Required string; observed in all 1 item; max length 101; sample begins `amplify:execute-plan loop has ready work but no subagents in flight`. | true | true |
| `blockingError.command` | Hook command tied to the blocking failure. | Required string; observed in all 1 item; max length 50; sample `node "${CLAUDE_PLUGIN_ROOT}/hooks/loop-resume.mjs"`. | true | false |
| `hookEvent` | Hook lifecycle event that produced the blocking error. | Required string; observed in all 1 item; max length 4; sample `Stop`. | true | false |
| `hookName` | Visible hook name. | Required string; observed in all 1 item; max length 4; sample `Stop`. | true | false |
| `toolUseID` | Hook or tool-call correlation identifier. | Required string; observed in all 1 item; max length 36; sample UUID-like ID. | false | false |
| `type` | Attachment subtype discriminator. | Required string; observed in all 1 item; constant sample `hook_blocking_error`. | false | false |

## Derived Car Form Content

| Field | Source Field | Contents |
| --- | --- | --- |
| Blocking Error | `blockingError` | Object containing blocking error fields. |
| Blocking Error Message | `blockingError.blockingError` | Blocking error string. |
| Command | `blockingError.command` | Hook command string. |
| Hook Event | `hookEvent` | Hook lifecycle event value. |
| Hook Name | `hookName` | Hook name value. |

## Message Navigation Item Design

```text
Attachment / Hook Blocking Error ...................................... 14:32:07
Stop | Stop | blocking | amplify:execute-plan loop has ready work but no subagents in flight...
```

Use the attachment-teal tone and render both category levels as full badges. The first line keeps the category/subtype label on the left and timestamp on the right; the second line starts with `hookName`, then shows `hookEvent`, blocking status, and the one-line `blockingError.blockingError` summary. Keep the preview clipped to one line so the blocking failure remains visible without expanding the card.

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [Hook Blocking Error]  14:32:07  agent/path                   |
|                                                              [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Hook                                                                           |
| +----------------+---------------------------------------------------------+   |
| | Hook Name      | Stop                                                    |   |
| | Hook Event     | Stop                                                    |   |
| | Command        | node "${CLAUDE_PLUGIN_ROOT}/hooks/loop-resume.mjs"      |   |
| +----------------+---------------------------------------------------------+   |
|                                                                                |
| Additional Context                                                             |
| +----------------+---------------------------------------------------------+   |
| | Parsed Context | empty                                                   |   |
| +----------------+---------------------------------------------------------+   |
|                                                                                |
| Failure                                                                        |
| +------------------------+-------------------------------------------------+   |
| | Blocking Status        | blocking                                        |   |
| | Blocking Error Message | amplify:execute-plan loop has ready work but    |   |
| |                        | no subagents in flight; re-priming the          |   |
| |                        | scheduling loop.                               |   |
| +------------------------+-------------------------------------------------+   |
+--------------------------------------------------------------------------------+
```

The card should place `blockingError.command` in the Hook section because this subtype has no top-level `command` field. For the observed shape, no `stdout` field exists, so Additional Context renders a compact empty state rather than repeating raw JSON. Failure uses `blockingError.blockingError` as the primary human-facing detail and presents the subtype status as blocking. Raw opens formatted raw JSON for the timeline item, and Copy JSON copies the raw payload.
