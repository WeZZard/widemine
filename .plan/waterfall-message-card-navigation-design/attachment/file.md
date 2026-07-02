# Attachment / File

## Fields
| Field | Purpose | Contents | Key | Summary |
|---|---|---|---|---|
| `content` | Container for the attachment payload. | Required object; count 37; contains `type` and `file`. | false | false |
| `content.file` | Container for file-specific payload fields. | Required object; count 37; contains file path, content text, and line counts. | false | false |
| `content.file.content` | File text shown as the primary preview and expandable body. | Required string; count 37; max length 11851; samples include TypeScript, markdown, shell, Rust, YAML, and JSON content. | true | true |
| `content.file.content.$json` | Parsed JSON value when the file content is valid JSON. | Optional object; count 9; present on JSON file attachments such as task graph files and schemas. | false | false |
| `content.file.filePath` | Absolute file path from the file payload. | Required string; count 37; max length 122; samples include repo paths and `/tmp/*.json` paths. | true | false |
| `content.file.numLines` | Number of included content lines. | Required number; count 37; samples include `8`, `28`, `66`, `181`, `231`, and `333`. | true | false |
| `content.file.startLine` | First included line number. | Required number; count 37; constant sample `1`. | true | false |
| `content.file.totalLines` | Total line count for the referenced file. | Required number; count 37; samples match the observed included line counts. | true | false |
| `content.type` | Content encoding marker inside the payload. | Required string; count 37; constant sample `text`. | false | false |
| `displayPath` | Compact path for navigation and card scanning. | Required string; count 37; max length 58; samples include `engine/stages/mine.ts`, `.opencode/agents/persona-maker.md`, and `../../../../tmp/product-driver-m4-graph.json`. | true | false |
| `filename` | Absolute file path at the attachment level. | Required string; count 37; max length 122; samples include repo paths and `/tmp/*.json` paths. | true | false |
| `type` | Raw attachment subtype discriminator. | Required string; count 37; constant sample `file`. | true | false |

## Derived Car Form Content
| Field | Contents |
|---|---|
| Display Path | `displayPath` |
| Filename | `filename` |
| File Path | `content.file.filePath` |
| File Content | `content.file.content` |
| Number Of Lines | `content.file.numLines` |
| Start Line | `content.file.startLine` |
| Total Lines | `content.file.totalLines` |
| Type | `type` |

## Message Navigation Item Design
```text
Attachment / File .................................................... 14:32:07
import path from "node:path"; import { createHash } from "node:crypto"; ...
```

Use the attachment-teal tone and render both category levels as full badges when badges are available. The first line keeps the category/subtype label on the left, a flexible dotted spacer, and the timestamp on the right. The second line uses the first meaningful line from `content.file.content`, clipped to one line; fall back to `displayPath`, then `filename`, when content is empty.

## Message Card Design
```text
+------------------------------------------------------------------------------------------------+
| Title Bar                                                                                      |
| o  [Attachment] [File]  14:32:07  agent/path                                  [Raw] [Copy JSON] |
+------------------------------------------------------------------------------------------------+
| Content Form                                                                                   |
|                                                                                                |
|  File Reference                                                                                |
|  +--------------+-----------------------------------------------------------------------------+ |
|  | Display Path | engine/stages/mine.ts                                                       | |
|  | Filename     | /Users/wezzard/Projects/product-driver/engine/stages/mine.ts               | |
|  | File Path    | /Users/wezzard/Projects/product-driver/engine/stages/mine.ts               | |
|  | Type         | file                                                                        | |
|  +--------------+-----------------------------------------------------------------------------+ |
|                                                                                                |
|  File Payload                                                                                  |
|  +-----------------+--------------------------------------------------------------------------+ |
|  | Start Line      | 1                                                                        | |
|  | Number Of Lines | 231                                                                      | |
|  | Total Lines     | 231                                                                      | |
|  +-----------------+--------------------------------------------------------------------------+ |
|                                                                                                |
|  File Content                                                                                  |
|  +--------------------------------------------------------------------------------------------+ |
|  | import path from "node:path";                                                              | |
|  | import { createHash } from "node:crypto";                                                  | |
|  | ...                                                                                        | |
|  +--------------------------------------------------------------------------------------------+ |
|  | [Expand full file content]                                                                 | |
|  +--------------------------------------------------------------------------------------------+ |
|                                                                                                |
|  Parsed JSON Content                                                                           |
|  +--------------------------------------------------------------------------------------------+ |
|  | Show only when `content.file.content.$json` is present; render as collapsed JSON tree.      | |
|  +--------------------------------------------------------------------------------------------+ |
+------------------------------------------------------------------------------------------------+
```

No array fields are present. Raw opens formatted raw JSON for this timeline item; Copy JSON copies the raw payload. Use message typography and smaller balanced monospace for paths and file content.
