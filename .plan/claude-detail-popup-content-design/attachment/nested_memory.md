# Detail Popup Content Design - Attachment / Nested Memory

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Content | `content.content` | Shows the captured nested memory text from the referenced memory file. | String; observed samples include CLAUDE.md and AGENTS.md instruction content, up to 4363 characters. | true |
| Content Differs From Disk | `content.contentDiffersFromDisk` | Indicates whether the captured memory text differs from the current file on disk. | Boolean; observed value is false. | true |
| Path | `content.path` | Identifies the source file whose memory content was captured. | Absolute file path string; observed values point to CLAUDE.md files. | true |
| Type | `content.type` | Identifies the nested memory scope recorded in the payload. | String; observed value is Project. | true |
| Display Path | `displayPath` | Provides the shortened user-facing path for the nested memory file. | Relative or shortened display path string, such as ../CLAUDE.md, apps/CLAUDE.md, or src/provider/CLAUDE.md. | true |
| Path | `path` | Preserves the top-level attachment path for metadata and raw inspection. | Absolute file path string, matching the referenced source path. | false |
| Type | `type` | Stores the raw routing discriminator already represented by the popup titlebar badges. | String; observed value is nested_memory. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Content | `content.content` | Use the `content.content` value from the message JSON. | Render as complete preserved multi-line text in a bounded scroll area with preserved line breaks. |
| Content Differs From Disk | `content.contentDiffersFromDisk` | Use the `content.contentDiffersFromDisk` value from the message JSON. | Render as a compact boolean value. |
| Path | `content.path` | Use the `content.path` value from the message JSON. | Render as a copyable monospace path with middle truncation when needed. |
| Type | `content.type` | Use the `content.type` value from the message JSON. | Render as a short scalar text value. |
| Display Path | `displayPath` | Use the `displayPath` value from the message JSON. | Render as a copyable monospace display path with middle truncation when needed. |

## Card Design

```text
+----------------------------------------------------------------------------+
| [Attachment] [Nested Memory]                                      [pin] [x] |
+----------------------------------------------------------------------------+
|                         Content | Metadata | Raw                            |
+----------------------------------------------------------------------------+
| Content                                                                    |
|   <content.content>                                                         |
|                                                                            |
| Content Differs From Disk     <content.contentDiffersFromDisk>              |
| Path                          <content.path>                                |
| Type                          <content.type>                                |
| Display Path                  <displayPath>                                 |
+----------------------------------------------------------------------------+
```
