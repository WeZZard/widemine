# Attachment / Queued Command

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `commandMode` | Queue command mode shown with the command details. | Required string; observed in all 356 items; samples include `prompt` and `task-notification`. | true | false |
| `prompt` | Queued command text or structured prompt payload used for the preview. | Required string or array; string form observed in 313 items with max length 21,660; array form observed in 43 items with max 2 items. | true | true |
| `prompt[]` | Structured prompt block group when `prompt` is an array. | Object item; observed 72 times across array-form prompts. | true | false |
| `prompt[].text` | Text inside a structured prompt block. | String; observed 72 times; max length 4,215; samples include user messages, IDE opened-file notices, and IDE selection notices. | true | false |
| `prompt[].type` | Structured prompt block type. | String; observed 72 times; sample value `text`. | false | false |
| `origin` | Origin container for the queued command when present. | Optional object; observed in 4 items. | false | false |
| `origin.kind` | Origin kind shown when present. | Optional string; observed in 4 items; sample value `human`. | true | false |
| `source_uuid` | Source correlation identifier. | Optional string; observed in 44 items; UUID samples include `d6e30235-fd3a-419a-98a3-2ab284b9e19a` and `b07fa214-96e3-45fa-9509-70714db64279`. | false | false |
| `type` | Attachment subtype discriminator. | Required constant string `queued_command`. | false | false |

## Derived Car Form Content

| Field | Source Field | Contents |
| --- | --- | --- |
| Command Mode | `commandMode` | Queue command mode. |
| Prompt | `prompt` | Queued command text or structured prompt payload. |
| Prompt Block | `prompt[]` | Structured prompt block group. |
| Prompt Text | `prompt[].text` | Text inside a structured prompt block. |
| Origin Kind | `origin.kind` | Origin kind. |

## Message Navigation Item Design

```text
Attachment / Queued Command ............................................ 05:14:03
No, I mean when you run the whole funnel, the funnel itself should detect...
```

Use the attachment-teal tone and render both category levels as full badges. The first line keeps `Attachment / Queued Command` on the left and the timestamp on the right. The second line uses `prompt` when it is a string; when `prompt` is an array, use the first non-empty `prompt[].text` value. Keep task-notification XML-like text unparsed and clipped to one preview line.

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [Queued Command]  05:14:03  agent/path       [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Queue Details                                                                  |
| +----------------+---------------------------------------------------------+   |
| | Command Mode   | prompt                                                  |   |
| | Origin Kind    | human                                                   |   |
| | Source UUID    | d6e30235-fd3a-419a-98a3-2ab284b9e19a                  |   |
| | Type           | queued_command                                          |   |
| +----------------+---------------------------------------------------------+   |
|                                                                                |
| Prompt                                                                         |
| +----------------+---------------------------------------------------------+   |
| | Prompt         | No, I mean when you run the whole funnel, the funnel    |   |
| |                | itself should detect if Google Chrome is installed     |   |
| |                | and launch it if necessary.                            |   |
| +----------------+---------------------------------------------------------+   |
|                                                                                |
| Structured Prompt                                                              |
| +------------------------------------------------------------------------------+
| | prompt[]                                                                     |
| | +----+----------+---------------------------------------------------------+ |
| | | #  | Type     | Text                                                    | |
| | +----+----------+---------------------------------------------------------+ |
| | | 1  | text     | <ide_opened_file>The user opened the file /Users/...  | |
| | |    |          | </ide_opened_file>                                    | |
| | | 2  | text     | Then push.                                            | |
| | +----+----------+---------------------------------------------------------+ |
| +------------------------------------------------------------------------------+
+--------------------------------------------------------------------------------+
```

Render the scalar `prompt` form as a wrapped message-text field. When `prompt` is an array, replace the scalar prompt row with the nested `prompt[]` table so each block keeps `prompt[].type` and `prompt[].text` together. Show `origin.kind` and `source_uuid` only when present; keep `source_uuid` secondary because it is a correlation identifier, not command content.
