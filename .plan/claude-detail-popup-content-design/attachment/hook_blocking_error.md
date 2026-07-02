## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Blocking Error | `blockingError.blockingError` | Provides the blocking failure result emitted by the hook. | String error text, observed as `amplify:execute-plan loop has ready work but no subagents in flight - re-priming the scheduling loop.` | true |
| Command | `blockingError.command` | Shows the command associated with the hook failure. | String shell command, observed as `node "${CLAUDE_PLUGIN_ROOT}/hooks/loop-resume.mjs"`. | true |
| Hook Event | `hookEvent` | Identifies the hook lifecycle event that produced the failure. | String value, observed as `Stop`. | true |
| Hook Name | `hookName` | Identifies the configured hook name that produced the failure. | String value, observed as `Stop`. | true |
| Tool Use ID | `toolUseID` | Trace identifier for correlation with other transcript records. | UUID string, observed as `08446c51-ea1e-4469-8f3d-926a536d9d40`. | false |
| Type | `type` | Routing discriminator for this attachment shape. | Constant string, observed as `hook_blocking_error`. | false |

## Derived Form Content

| Form Field | Raw Path | Rendering |
| --- | --- | --- |
| Blocking Error | `blockingError.blockingError` | Render inside a `Blocking Error` nested form group as complete pre-wrapped multiline text in a bounded scroll area. |
| Command | `blockingError.command` | Render inside the same `Blocking Error` nested form group as compact wrapping monospace. |
| Hook Event | `hookEvent` | Render as a compact scalar field. |
| Hook Name | `hookName` | Render as a compact scalar field. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [Attachment] [Hook Blocking Error]                              [pin] [x] |
+--------------------------------------------------------------------------+
|                         Content | Metadata | Raw                         |
+--------------------------------------------------------------------------+
| Blocking Error                                                           |
|   Blocking Error                                                         |
|   amplify:execute-plan loop has ready work but no subagents in flight... |
|                                                                          |
|   Command                                                                |
|   node "${CLAUDE_PLUGIN_ROOT}/hooks/loop-resume.mjs"                     |
|                                                                          |
| Hook Event        Stop                                                    |
| Hook Name         Stop                                                    |
+--------------------------------------------------------------------------+
```
