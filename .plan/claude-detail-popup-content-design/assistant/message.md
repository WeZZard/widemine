# Detail Popup Content Design - Assistant / Message

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Text | `text` | Primary assistant message body shown to the end user. | String transcript text; observed in 39,271 messages, with long markdown-capable content. | true |
| Text JSON | `text.$json` | Parser-detected JSON object embedded in the text field; kept out of Content because `$json` is a derived path segment. | Object; observed in 9 messages across two parsed JSON shapes. | false |
| Done Substantive | `text.$json.doneSubstantive` | Parser-detected progress value embedded in text; forced non-key by `$json`. | Number; examples include 1023, 864, and 704. | false |
| Groups | `text.$json.groups` | Parser-detected grouped payload embedded in text; forced non-key by `$json`. | Array; observed with up to 104 items. | false |
| Groups Items | `text.$json.groups[]` | Parser-detected group item objects embedded in text; forced non-key by `$json`. | Object items; observed 80 total items. | false |
| Remaining Substantive | `text.$json.remainingSubstantive` | Parser-detected progress value embedded in text; forced non-key by `$json`. | Number; examples include 648, 807, and 967. | false |
| Renames | `text.$json.renames` | Parser-detected rename list embedded in text; forced non-key by `$json`. | Array; observed with up to 36 items. | false |
| Renames Items | `text.$json.renames[]` | Parser-detected rename item objects embedded in text; forced non-key by `$json`. | Object items; observed 10 total items. | false |
| Repo Abs | `text.$json.repoAbs` | Parser-detected repository path embedded in text; forced non-key by `$json` and not a Content-section result field. | String path; observed max length 84. | false |
| Total Substantive | `text.$json.totalSubstantive` | Parser-detected total value embedded in text; forced non-key by `$json`. | Number; observed value 1819. | false |
| Total Trivial | `text.$json.totalTrivial` | Parser-detected total value embedded in text; forced non-key by `$json`. | Number; observed value 3919. | false |
| Type | `type` | Routing metadata owned by the popup titlebar and raw metadata views. | String value `text`; observed in 39,271 shape records. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Text | `text` | Read directly from the message JSON object's `text` field. | Render as the assistant message body with transcript typography; preserve markdown, whitespace, and code blocks inside a bounded scroll area; do not add expand/collapse controls. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [Assistant] [Message]                                           [pin] [x] |
+--------------------------------------------------------------------------+
|                      Content | Metadata | Raw                            |
+--------------------------------------------------------------------------+
| Text                                                                     |
| <assistant message body from text>                                        |
+--------------------------------------------------------------------------+
```
