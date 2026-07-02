# Detail Popup Content Design - Attachment / Edited Text File

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Filename | `filename` | Identifies the edited text file referenced by the attachment. | String file path, observed up to 128 characters. | true |
| Snippet | `snippet` | Provides the user-visible excerpt of the edited file. | String text preview of file contents, often line-numbered and truncated. | true |
| Type | `type` | Supports attachment subtype routing outside the content form. | String subtype marker, observed as `edited_text_file`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Filename | `filename` | Use the raw `filename` string. | Render as a copyable monospace path with middle truncation when space is limited. |
| Snippet | `snippet` | Use the raw `snippet` string. | Render as a complete prewrapped monospace text preview with preserved spacing inside a bounded scroll area; do not add expand/collapse controls. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [Attachment] [Edited Text File]                                 [pin] [x] |
+--------------------------------------------------------------------------+
|                         Content | Metadata | Raw                         |
+--------------------------------------------------------------------------+
| Filename                                                                 |
| /Users/wezzard/CLAUDE.md                                                 |
|                                                                          |
| Snippet                                                                  |
| +----------------------------------------------------------------------+ |
| | 1 # CLAUDE.md                                                        | |
| | 2                                                                    | |
| | 3 ## Introduction                                                    | |
| | <continues in scroll area with preserved line breaks>                 | |
| +----------------------------------------------------------------------+ |
+--------------------------------------------------------------------------+
```
