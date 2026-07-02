# Attachment / Todo Reminder

## Fields
| Field | Purpose | Contents | Key | Summary |
|---|---|---|---|---|
| `content` | Reminder item array and empty-state source. | Required array; count 493; empty in 476 observations, populated in 17 observations; max 11 items. | true | false |
| `content[]` | Repeating todo reminder item group for nested content rows. | Object item; 128 observed items; contains `activeForm`, `content`, and `status`. | true | false |
| `content[].activeForm` | Current active wording for the todo reminder item. | String; count 128; max length 54; samples include `Writing task-graph JSON schema` and `Reconciling engine field names to snake_case`. | true | false |
| `content[].content` | Visible todo reminder text used for preview and item rows. | String; count 128; max length 104; samples include `Add schemas/task-graph.schema.json (folded graph schema)` and `engine-fields: reconcile concurrency.mjs to snake_case`. | true | true |
| `content[].status` | Todo reminder status value shown beside each item. | String; count 128; max length 11; samples include `completed` and `in_progress`. | true | false |
| `itemCount` | Count of reminder items, including the empty state. | Required number; count 493; samples include `0`, `11`, `3`, `5`, `9`, and `4`. | true | false |
| `type` | Attachment subtype discriminator. | Required constant string `todo_reminder`; rendered as the Todo Reminder badge. | false | false |

## Derived Car Form Content
| Form Field | Source Field | Contents |
|---|---|---|
| Content | `content` | Reminder item array. |
| Todo Item | `content[]` | Repeated reminder item object. |
| Active Form | `content[].activeForm` | Active form string. |
| Reminder Text | `content[].content` | Todo reminder text. |
| Status | `content[].status` | Todo status string. |
| Item Count | `itemCount` | Reminder item count. |

## Message Navigation Item Design
```text
Attachment / Todo Reminder                                             14:27:09
codex-driver: add agents/codex-driver.md (general headless Codex driver)
```

Use `content[].content` from the first item as the second-line summary contents when the array is populated. When `content` is empty, show `No active todo reminders` as the second line and keep the first line unchanged.

## Message Card Design
```text
+--------------------------------------------------------------------------------+
| Attachment / Todo Reminder  14:27:09  agent/path              [Raw] [Copy JSON]|
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
|  Reminder                                                                      |
|  +-------------+------------------------------------------------------------+  |
|  | Item Count  | 5                                                          |  |
|  +-------------+------------------------------------------------------------+  |
|                                                                                |
|  Content                                                                       |
|  +----+-------------+--------------------------------------+----------------+  |
|  | #  | Status      | Reminder Text                        | Active Form    |  |
|  +----+-------------+--------------------------------------+----------------+  |
|  | 1  | completed   | Add schemas/task-graph.schema.json   | Writing task-  |  |
|  |    |             | (folded graph schema)                | graph JSON...  |  |
|  | 2  | completed   | engine-fields: reconcile             | Reconciling    |  |
|  |    |             | concurrency.mjs to snake_case        | engine field...|  |
|  | 3  | in_progress | codex-driver: add agents/codex-      | Writing codex- |  |
|  |    |             | driver.md                            | driver agent   |  |
|  | ...| ...         | ...                                  | ...            |  |
|  +----+-------------+--------------------------------------+----------------+  |
|                                                                                |
|  Empty content: show Item Count `0` and replace the nested Content table with  |
|  `No active todo reminders`. Raw opens formatted raw JSON for this timeline    |
|  item; Copy JSON copies the raw payload.                                       |
+--------------------------------------------------------------------------------+
```
