# Attachment / Plan File Reference Waterfall Surface Design

## Fields
| Field | Purpose | Contents | Key | Summary |
|---|---|---|---|---|
| `planContent` | Plan markdown content for preview and expansion. | Required string; count 9; max length 18551; samples begin with plan headings and execution instructions. | true | true |
| `planFilePath` | Absolute path to the referenced plan file. | Required string; count 9; max length 76; samples are `.md` files under `/Users/wezzard/.claude/plans/`. | true | false |
| `type` | Attachment subtype discriminator and operation marker. | Required constant string `plan_file_reference`; rendered as the Plan File Reference badge or metadata value. | true | false |

## Derived Car Form Content
| Form Field | Source Field | Control | Contents |
|---|---|---|---|
| Plan Content | `planContent` | Expandable wrapped text | First meaningful content line plus expandable full plan markdown. |
| Plan File Path | `planFilePath` | Monospace path field | Absolute plan file path; middle-truncate when needed. |
| Type | `type` | Compact scalar | Operation marker `plan_file_reference`. |

## Message Navigation Item Design
```text
+--------------------------------------------------------------------------------+
| o  [Attachment] [Plan File Reference]  14:32:07  # product-driver              |
+--------------------------------------------------------------------------------+
  activity dot   full badges                         timestamp   one-line preview
  tone: attachment-teal; use the same full badge style for both category levels

Preview rules:
- Use the first meaningful line from `planContent`.
- Strip markdown quoting noise when possible, but preserve the leading heading text.
- Fall back to the basename from `planFilePath` when `planContent` is unavailable.
```

## Message Card Design
```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [Plan File Reference]  14:32:07  agent/path  [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
|  File Reference                                                                |
|  +----------------+---------------------------------------------------------+  |
|  | Plan File Path | /Users/wezzard/.claude/plans/cached-skipping-moth.md    |  |
|  | Type           | plan_file_reference                                    |  |
|  +----------------+---------------------------------------------------------+  |
|                                                                                |
|  Plan Content                                                                  |
|  +--------------------------------------------------------------------------+  |
|  | # product-driver - Per-Idea Process Graph (Milestone 4)                  |  |
|  | > For Claude:                                                            |  |
|  | > You MUST use amplify:execute-plan to execute this plan.                |  |
|  | ...                                                                      |  |
|  +--------------------------------------------------------------------------+  |
|  | [Expand full plan content]                                               |  |
|  +--------------------------------------------------------------------------+  |
|                                                                                |
|  No array fields are present. Raw button opens formatted raw JSON for this     |
|  timeline item; Copy JSON copies the raw payload. Use message typography and   |
|  smaller balanced monospace for paths, commands, and command-like fragments.   |
+--------------------------------------------------------------------------------+
```
