# Detail Popup Content Design - Attachment / Compact File Reference

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Display Path | `displayPath` | Shows the compact path presented for the referenced file. | String path value such as `claude/amplify/scripts/task.test.mjs`, `src/tool/agent.rs`, or `../../../../tmp/rbx-whiteboard-graph.json`. | true |
| Filename | `filename` | Provides the full file path behind the compact reference. | String absolute path value such as `/Users/wezzard/Artifacts/Repositories/com.github/WeZZard/skills/claude/amplify/scripts/task.test.mjs` or `/tmp/rbx-whiteboard-graph.json`. | true |
| Type | `type` | Routes the attachment renderer and titlebar subtype. | String value `compact_file_reference`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Display Path | `displayPath` | Use the message `displayPath` value. | Render as a single-line copyable path with middle truncation when needed. |
| Filename | `filename` | Use the message `filename` value. | Render as a single-line copyable path with middle truncation when needed. |

## Card Design

```text
+------------------------------------------------------------------------+
| [Attachment] [Compact File Reference]                        [pin] [x] |
+------------------------------------------------------------------------+
|                         Content | Metadata | Raw                       |
+------------------------------------------------------------------------+
| Display Path   claude/amplify/scripts/task.test.mjs                    |
| Filename       /Users/wezzard/.../claude/amplify/scripts/task.test.mjs |
+------------------------------------------------------------------------+
```
