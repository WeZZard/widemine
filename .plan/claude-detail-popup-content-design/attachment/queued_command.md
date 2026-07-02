# Detail Popup Content Design - Attachment / Queued Command

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Command Mode | `commandMode` | Identifies how the queued command should be interpreted. | String; observed values include `prompt` and `task-notification`. | true |
| Prompt | `prompt` | Carries the queued command content. | String prompt text in most records; array container in records whose item content is flattened under `prompt[]`. | true |
| Prompt Items | `prompt[]` | Structural item container for array-form prompt blocks. | Object items; observed when `prompt` is an array with up to 2 items. | false |
| Text | `prompt[].text` | Carries each visible text block inside an array-form prompt. | String prompt block text; observed max length 4215. | true |
| Type | `prompt[].type` | Identifies the array prompt block kind. | String; observed value `text`. | false |
| Origin | `origin` | Structural container for origin metadata. | Object; child field observed at `origin.kind`. | false |
| Kind | `origin.kind` | Records the origin class for the queued command. | String; observed value `human`. | false |
| Source UUID | `source_uuid` | Links the queued command to a source transcript record. | UUID string; observed max length 36. | false |
| Type | `type` | Routes the attachment payload to the queued command renderer. | String; observed value `queued_command`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Command Mode | `commandMode` | Read directly from `commandMode`. | Render as a compact single-line value. |
| Prompt | `prompt` | Read directly from `prompt`; when it is an array, use the child rows from `prompt[].text`. | Render scalar prompts as pre-wrapped multiline text; render array prompts as a nested `Prompt` group. |
| Text | `prompt[].text` | Read each `text` value from array-form `prompt` items. | Render inside the nested `Prompt` group under a `Text` column, preserving item order and line breaks. |

## Card Design

```text
+----------------------------------------------------------------------------+
| [Attachment] [Queued Command]                                    [pin] [x] |
+----------------------------------------------------------------------------+
|                         Content | Metadata | Raw                           |
+----------------------------------------------------------------------------+
| Command Mode        <commandMode>                                          |
| Prompt              <prompt string when scalar>                            |
|                                                                            |
| Prompt                                                                     |
| +----------------------------------------------------------------------+   |
| | Text                                                                 |   |
| | <prompt[].text>                                                      |   |
| | <prompt[].text>                                                      |   |
| +----------------------------------------------------------------------+   |
+----------------------------------------------------------------------------+
```
