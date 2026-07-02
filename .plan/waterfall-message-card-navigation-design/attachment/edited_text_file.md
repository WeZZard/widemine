# Attachment / Edited Text File

## Fields
| Field | Purpose | Contents | Key | Summary |
|---|---|---|---|---|
| `filename` | Edited file path shown for orientation and drill-in. | Required string; count 235; max length 128; samples include `/Users/wezzard/CLAUDE.md`, plan markdown files, source files, configs, and dotfiles. | true | false |
| `snippet` | Visible edited-file excerpt used for preview and content review. | Required string; count 235; max length 8222; line-numbered excerpt text from the edited file. | true | true |
| `type` | Attachment subtype discriminator. | Required constant string `edited_text_file`. | false | false |

## Derived Car Form Content
| Form Field | Source Field | Contents |
|---|---|---|
| Filename | `filename` | Value of `filename`. |
| Snippet | `snippet` | Value of `snippet`. |

## Message Navigation Item Design
```text
Attachment / Edited Text File ........................................ 14:32:07
1 # CLAUDE.md 2 3 ## Introduction 4 5 I'm WeZZard. 6 7 ## Communication...
```

Use the attachment-teal tone and render both category levels as full badges when badges are available. The second line uses `snippet`, clipped to one line; fall back to `filename` only when `snippet` is empty or unavailable.

## Message Card Design
```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [Edited Text File]  14:32:07  agent/path     [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
|  File Reference                                                                |
|  +----------+---------------------------------------------------------------+  |
|  | Filename | /Users/wezzard/CLAUDE.md                                      |  |
|  | Type     | edited_text_file                                             |  |
|  +----------+---------------------------------------------------------------+  |
|                                                                                |
|  Snippet                                                                       |
|  +--------------------------------------------------------------------------+  |
|  | 1 # CLAUDE.md 2 3 ## Introduction 4 5 I'm WeZZard. 6 7 ## Communication |  |
|  | Style 8 9 You **MUST** use American English. 10 You **MUST** always...  |  |
|  +--------------------------------------------------------------------------+  |
|  | [Expand full snippet]                                                    |  |
|  +--------------------------------------------------------------------------+  |
+--------------------------------------------------------------------------------+
```

No array fields are present. Raw opens formatted raw JSON for this timeline item; Copy JSON copies the raw timeline item. Use smaller balanced monospace for paths and snippet text, preserving the line-numbered excerpt formatting.
