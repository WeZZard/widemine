# Attachment / Nested Memory

## Fields
| Field | Purpose | Contents | Key | Summary |
|---|---|---|---|---|
| `content` | Container for the nested memory file reference data. | Required object; count 29; contains `content`, `contentDiffersFromDisk`, `path`, and `type`. | false | false |
| `content.content` | Nested memory file text shown as the primary preview and expandable body. | Required string; count 29; max length 4363; samples begin with headings such as `# CLAUDE.md`, `# AGENTS.md`, `# Testing Rules`, and `# Provider Tool Testing Principles`. | true | true |
| `content.contentDiffersFromDisk` | Boolean status indicating whether the captured memory content differs from the file on disk. | Required bool; count 29; sample `false`. | true | false |
| `content.path` | Absolute path to the memory file inside the nested content object. | Required string; count 29; max length 85; samples include `/Users/wezzard/.claude/plugins/cache/readycheck/readycheck/0.0.3/CLAUDE.md` and project `CLAUDE.md` paths. | true | false |
| `content.type` | Human-visible memory scope or operation label from the nested content object. | Required string; count 29; max length 7; sample `Project`. | true | false |
| `displayPath` | Compact path shown in navigation and card scanning. | Required string; count 29; max length 64; samples include `../CLAUDE.md`, `apps/CLAUDE.md`, `tests/CLAUDE.md`, and `src/provider/CLAUDE.md`. | true | false |
| `path` | Top-level absolute path to the memory file. | Required string; count 29; max length 85; samples match `content.path`. | false | false |
| `type` | Raw attachment subtype discriminator. | Required string; count 29; constant sample `nested_memory`. | false | false |

## Derived Car Form Content
| Field | Source Field | Contents |
|---|---|---|
| Memory Content | `content.content` | Value of `content.content`. |
| Content Differs From Disk | `content.contentDiffersFromDisk` | Value of `content.contentDiffersFromDisk`. |
| Content Path | `content.path` | Value of `content.path`. |
| Content Type | `content.type` | Value of `content.type`. |
| Display Path | `displayPath` | Value of `displayPath`. |

## Message Navigation Item Design
```text
Attachment / Nested Memory ............................................. 14:32:07
# CLAUDE.md This directory provides Claude Code plugin. ## Licensing...
```

Use the attachment-teal tone and render both category levels as full badges when badges are available. The second line uses the first meaningful line from `content.content`, clipped to one line; fall back to `displayPath`, then `content.path`.

## Message Card Design
```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [Nested Memory]  14:32:07  agent/path        [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
|  File Reference                                                                |
|  +--------------+-----------------------------------------------------------+  |
|  | Display Path | ../CLAUDE.md                                             |  |
|  | Path         | /Users/wezzard/.claude/plugins/cache/.../CLAUDE.md       |  |
|  | Type         | nested_memory                                           |  |
|  +--------------+-----------------------------------------------------------+  |
|                                                                                |
|  Content                                                                       |
|  +---------------------------+----------------------------------------------+  |
|  | Type                      | Project                                      |  |
|  | Path                      | /Users/wezzard/.claude/plugins/.../CLAUDE.md |  |
|  | Content Differs From Disk | false                                        |  |
|  +---------------------------+----------------------------------------------+  |
|                                                                                |
|  Memory Content                                                                |
|  +--------------------------------------------------------------------------+  |
|  | # CLAUDE.md This directory provides Claude Code plugin. ## Licensing     |  |
|  | ReadyCheck Skills is a public preview distribution channel. The skill... |  |
|  +--------------------------------------------------------------------------+  |
|  | [Expand full memory content]                                             |  |
|  +--------------------------------------------------------------------------+  |
+--------------------------------------------------------------------------------+
```

No array fields are present. Raw opens formatted raw JSON for this timeline item; Copy JSON copies the raw timeline item. Use message typography and smaller balanced monospace for paths and memory content.
