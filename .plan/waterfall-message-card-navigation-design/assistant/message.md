# Assistant / Message

## Fields
| Field | Purpose | Contents | Key | Summary |
|---|---|---|---|---|
| `text` | Assistant-authored message content for preview, transcript reading, and card expansion. | Required string; count 40630; max length 74224; contains normal prose or occasional JSON text. | true | true |
| `text.$json` | Parsed object available when `text` is valid JSON. | Object helper; count 9; parent for parsed JSON fields only. | false | false |
| `text.$json.doneSubstantive` | Parsed JSON numeric field for the message body. | Number; count 8; samples include `1023`, `864`, and `704`. | true | false |
| `text.$json.groups` | Parsed JSON array field for the message body. | Array; count 8; max 104 items observed. | true | false |
| `text.$json.groups[]` | Repeated object item inside `text.$json.groups`. | Object rows; 80 observed rows in the compiled scan. | false | false |
| `text.$json.remainingSubstantive` | Parsed JSON numeric field for the message body. | Number; count 8; samples include `648`, `807`, and `967`. | true | false |
| `text.$json.renames` | Parsed JSON array field for the message body. | Array; count 1; max 36 items observed. | true | false |
| `text.$json.renames[]` | Repeated object item inside `text.$json.renames`. | Object rows; 10 observed rows in the compiled scan. | false | false |
| `text.$json.repoAbs` | Parsed JSON path string for the message body. | String; count 8; max length 84; sample is an absolute repository path. | true | false |
| `text.$json.totalSubstantive` | Parsed JSON numeric field for the message body. | Number; count 8; sample `1819`. | true | false |
| `text.$json.totalTrivial` | Parsed JSON numeric field for the message body. | Number; count 8; sample `3919`. | true | false |
| `type` | Message content discriminator used by the renderer. | Required constant string `text`; count 40630. | true | false |

## Derived Car Form Content
| Form Field | Source Field | Control | Contents |
|---|---|---|---|
| Message Text | `text` | Wrapped message typography | Full assistant message string; first meaningful line supplies the summary. |
| Done Substantive | `text.$json.doneSubstantive` | Compact number | Numeric value when parsed JSON is present. |
| Groups | `text.$json.groups` | Counted nested table | Array value when parsed JSON is present. |
| Remaining Substantive | `text.$json.remainingSubstantive` | Compact number | Numeric value when parsed JSON is present. |
| Renames | `text.$json.renames` | Counted nested table | Array value when parsed JSON is present. |
| Repo Abs | `text.$json.repoAbs` | Monospace path | Absolute repository path string when parsed JSON is present. |
| Total Substantive | `text.$json.totalSubstantive` | Compact number | Numeric value when parsed JSON is present. |
| Total Trivial | `text.$json.totalTrivial` | Compact number | Numeric value when parsed JSON is present. |
| Type | `type` | Compact scalar | Required constant string `text`. |

## Message Navigation Item Design
```text
Assistant / Message                                                14:32:07
I'll find both repos with `gh` and clone them to $HOME/Artifacts/...

line 1: category / subtype                                         time
line 2: first meaningful contents from `text`
tone: assistant-blue

Preview rules:
- Use the first meaningful line from `text`.
- Preserve transcript typography cues such as inline code while truncating to one row.
- If `text` is JSON, use the compact first line of the raw `text` value for the navigation summary.
```

## Message Card Design
```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| Assistant / Message                                  14:32:07  agent/path       |
|                                                        [Raw] [Copy JSON]        |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
|  Message                                                                       |
|  +----------------+---------------------------------------------------------+  |
|  | Message Text   | I'll find both repos with `gh` and clone them to the    |  |
|  |                | location specified in your CLAUDE.md...                |  |
|  | Type           | text                                                    |  |
|  +----------------+---------------------------------------------------------+  |
|                                                                                |
|  Parsed Text JSON (when present)                                               |
|  +----------------------+--------------------------------------------------+  |
|  | Repo Abs             | /Users/wezzard/Artifacts/Repositories/...        |  |
|  | Total Substantive    | 1819                                             |  |
|  | Done Substantive     | 1023                                             |  |
|  | Remaining Substantive| 648                                              |  |
|  | Total Trivial        | 3919                                             |  |
|  +----------------------+--------------------------------------------------+  |
|                                                                                |
|  Groups (104 max)                                                              |
|  +----+-------------------------+-----------------------------------------+  |
|  | #  | Source                  | Contents                                |  |
|  +----+-------------------------+-----------------------------------------+  |
|  | 1  | text.$json.groups[0]    | Expandable raw group object             |  |
|  | 2  | text.$json.groups[1]    | Expandable raw group object             |  |
|  | .. | ...                     | ...                                     |  |
|  +----+-------------------------+-----------------------------------------+  |
|                                                                                |
|  Renames (36 max)                                                              |
|  +----+--------------------------+----------------------------------------+  |
|  | #  | Source                   | Contents                               |  |
|  +----+--------------------------+----------------------------------------+  |
|  | 1  | text.$json.renames[0]    | Expandable raw rename object           |  |
|  | 2  | text.$json.renames[1]    | Expandable raw rename object           |  |
|  | .. | ...                      | ...                                    |  |
|  +----+--------------------------+----------------------------------------+  |
|                                                                                |
|  Raw button opens formatted raw JSON for this timeline item. Copy JSON copies  |
|  the raw payload. Use assistant-blue tone, normal transcript typography for    |
|  prose, and smaller balanced monospace for JSON, paths, and inline code.       |
+--------------------------------------------------------------------------------+
```
