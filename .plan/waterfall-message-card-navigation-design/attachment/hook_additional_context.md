# Attachment / Hook Additional Context

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `content` | Additional context container and count source. | Required array; observed in all 2,421 items; max 1 item. | true | false |
| `content[]` | Human-facing hook-provided context text. | Required string; observed in all 2,421 items; max length 7,525; samples include skill instructions, plan-mode notices, and IDE diagnostics. | true | true |
| `hookEvent` | Hook lifecycle event that produced the context. | Required string; observed in all 2,421 items; max length 18; samples include `SessionStart`, `UserPromptSubmit`, `PostToolUseFailure`, `PostToolUse`, and `Stop`. | true | false |
| `hookName` | Visible hook name, including tool-specific suffixes when present. | Required string; observed in all 2,421 items; max length 27; samples include `SessionStart`, `UserPromptSubmit`, `PostToolUseFailure:WebFetch`, `PostToolUse:EnterPlanMode`, and `PostToolUseFailure:Bash`. | true | false |
| `toolUseID` | Hook or tool-call correlation identifier. | Required string; observed in all 2,421 items; max length 41; samples include `SessionStart`, `hook-...`, and `toolu_...`. | false | false |
| `type` | Attachment subtype discriminator. | Required string; constant sample `hook_additional_context`. | false | false |

## Derived Car Form Content

| Field | Source Field | Contents |
| --- | --- | --- |
| Content | `content` | Additional context count. |
| Content Item | `content[]` | Human-facing hook-provided context text. |
| Hook Event | `hookEvent` | Hook lifecycle event. |
| Hook Name | `hookName` | Visible hook name. |

## Message Navigation Item Design

```text
Attachment / Hook Additional Context .................................... 14:32:07
PostToolUseFailure:Bash | <ide_diagnostics>[ { "filePath": "/Users/..." } ]
```

Use the attachment-teal tone and render both category levels as full badges. The first line keeps the category/subtype label on the left and the timestamp on the right; the second line starts with `hookName` and then shows the first meaningful `content[]` line, clipped to one preview line.

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [Hook Additional Context]  14:32:07  agent/path              |
|                                                              [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Hook                                                                           |
| +----------------+---------------------------------------------------------+   |
| | Hook Event     | PostToolUseFailure                                      |   |
| | Hook Name      | PostToolUseFailure:Bash                                 |   |
| | Tool Use ID    | hook-280d34b8-fc4d-414d-b7d9-c0cadcd23271              |   |
| | Type           | hook_additional_context                                |   |
| +----------------+---------------------------------------------------------+   |
|                                                                                |
| Additional Context                                                             |
| +----------------+---------------------------------------------------------+   |
| | Content (1)    |                                                         |   |
| | content[]      | <ide_diagnostics>[                                     |   |
| |                |   { "filePath": "/Users/wezzard/...",                  |   |
| |                |     "line": 23,                                       |   |
| |                |     "message": "MD040/fenced-code-language..." }      |   |
| |                | ]                                                     |   |
| +----------------+---------------------------------------------------------+   |
+--------------------------------------------------------------------------------+
```

Keep the hook section compact so `hookEvent` and `hookName` stay scannable. Render `content[]` as a nested table row under the `content` array because the raw shape is an array, even though current samples contain one item; wrap long diagnostics or instruction text in message typography and avoid duplicating the same raw text outside the content table.
