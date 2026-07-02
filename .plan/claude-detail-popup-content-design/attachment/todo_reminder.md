# Detail Popup Content Design - Attachment / Todo Reminder

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Content | `content` | Holds the todo reminder item array, including the empty-list case. | Array. Empty in 476 observations; populated in 17 observations with up to 11 object items. | true |
| Content Item | `content[]` | Groups the fields for each todo reminder item. | Object item. Observed 128 items with `activeForm`, `content`, and `status` child fields. | true |
| Active Form | `content[].activeForm` | Shows the short current-action form for each todo reminder item. | String. Examples include `Writing task-graph JSON schema`, `Reconciling engine field names to snake_case`, and `Writing codex-driver agent`; observed max length 54. | true |
| Content | `content[].content` | Shows the todo reminder text for each item. | String. Examples include `Add schemas/task-graph.schema.json (folded graph schema)` and `engine-fields: reconcile concurrency.mjs to snake_case`; observed max length 104. | true |
| Status | `content[].status` | Shows the recorded todo state for each item. | String. Samples include `completed` and `in_progress`; observed max length 11. | true |
| Item Count | `itemCount` | Shows how many todo reminder items are present. | Number. Samples include `0`, `11`, `3`, `5`, `9`, and `4`. | true |
| Type | `type` | Routes this attachment shape; the popup titlebar already shows category identity. | String. Sample is `todo_reminder`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Content | `content` | Use the array from the payload; child rows come from `content[]`. | Render as a `Content` group with a nested table; when empty, render `None`. |
| Content Item | `content[]` | Use each object item in `content` in source order. | Render each item as one nested table row; never split child fields into unrelated top-level rows. |
| Active Form | `content[].activeForm` | Use the value from each todo reminder item. | Render in the `Active Form` column inside the `Content` nested table. |
| Content | `content[].content` | Use the value from each todo reminder item. | Render in the `Content` column as wrapped text inside the `Content` nested table. |
| Status | `content[].status` | Use the value from each todo reminder item. | Render in the `Status` column as a compact value inside the `Content` nested table. |
| Item Count | `itemCount` | Use the scalar count from the payload. | Render as a compact number row before the nested `Content` group. |

## Card Design

```text
+------------------------------------------------------------------------------+
| [Attachment] [Todo Reminder]                                      [pin] [x]  |
+------------------------------------------------------------------------------+
|                         Content | Metadata | Raw                             |
+------------------------------------------------------------------------------+
| Item Count   11                                                              |
| Content                                                                      |
|   | Active Form                | Content                    | Status      |  |
|   | Writing task-graph JSON... | Add schemas/task-graph...  | completed   |  |
|   | Reconciling engine names...| engine-fields: reconcile   | in_progress |  |
+------------------------------------------------------------------------------+
```
