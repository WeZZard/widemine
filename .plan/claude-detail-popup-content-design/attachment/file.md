# Detail Popup Content Design - Attachment / File

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Content | `content` | Container for the attachment payload; child paths define the Content form. | Object observed in all file attachment shapes. | false |
| File | `content.file` | Container for attached file details; child paths carry the visible file reference. | Object observed in all file attachment shapes. | false |
| Content | `content.file.content` | Carries the attached file text shown to the user. | String file body; observed across plain text, code, and JSON text, with long values. | true |
| JSON | `content.file.content.$json` | Parser-expanded JSON object for JSON-backed file content; kept out of Content because `$json` is an internal child path. | Object present only for JSON file attachments. | false |
| File Path | `content.file.filePath` | Identifies the absolute source path for the attached file content. | String path; examples include `/tmp/product-driver-m4-graph.json` and project file paths. | true |
| Num Lines | `content.file.numLines` | States how many file lines are included in the attachment content. | Number; observed values include `8`, `28`, `66`, `231`, and `333`. | true |
| Start Line | `content.file.startLine` | States the first included line for interpreting the attachment as a full file or excerpt. | Number; observed value is `1`. | true |
| Total Lines | `content.file.totalLines` | States the source file line count for interpreting whether the included content is complete. | Number; usually matches `content.file.numLines` in samples. | true |
| Type | `content.type` | Records the nested payload format for metadata and raw inspection. | String value `text`. | false |
| Display Path | `displayPath` | Provides the user-facing shortened path for the attached file. | Relative or shortened path string, such as `engine/stages/mine.ts` or `../../../../tmp/product-driver-m4-graph.json`. | true |
| Filename | `filename` | Provides the top-level filename value for metadata and raw inspection. | Absolute file path string, often duplicating `content.file.filePath`. | false |
| Type | `type` | Routes the attachment subtype; the titlebar owns category display. | String value `file`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Display Path | `displayPath` | Direct value from `displayPath`. | Render as the primary copyable path with middle truncation when constrained. |
| File Path | `content.file.filePath` | Direct value from `content.file.filePath`. | Render as a copyable monospace absolute path with middle truncation when constrained. |
| Num Lines | `content.file.numLines` | Direct number from `content.file.numLines`. | Render as a compact numeric row. |
| Start Line | `content.file.startLine` | Direct number from `content.file.startLine`. | Render as a compact numeric row. |
| Total Lines | `content.file.totalLines` | Direct number from `content.file.totalLines`. | Render as a compact numeric row. |
| Content | `content.file.content` | Direct string from `content.file.content`. | Render as a complete pre-wrapped monospace file preview with preserved newlines inside a bounded scroll area; do not add expand/collapse controls. |

## Card Design

```text
+----------------------------------------------------------------------------+
| [Attachment] [File]                                               [pin] [x] |
+----------------------------------------------------------------------------+
|                         Content | Metadata | Raw                            |
+----------------------------------------------------------------------------+
| Display Path   engine/stages/mine.ts                                       |
| File Path      /Users/wezzard/Projects/product-driver/engine/stages/mine.ts |
| Num Lines      231                                                          |
| Start Line     1                                                            |
| Total Lines    231                                                          |
| Content                                                                    |
|   +----------------------------------------------------------------------+ |
|   | import path from "node:path";                                        | |
|   | import { createHash } from "node:crypto";                            | |
|   | <continues in scroll area with preserved line breaks>                | |
|   +----------------------------------------------------------------------+ |
+----------------------------------------------------------------------------+
```
