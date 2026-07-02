# Attachment / Task Reminder

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `content` | Reminder task array and empty-state source. | Required array; observed in all 1,045 items; 983 are empty arrays and 62 contain task rows; max 7 items. | true | false |
| `content[]` | Individual reminder task object. | Object; observed 245 times across populated reminders. | true | false |
| `content[].activeForm` | Current-action wording for the task. | Required string on task rows; count 245; max length 37; samples include `Parsing dependency graph`, `Building whole-graph driver`, `Building dependency graph`, and `Adding Gpt reading model variant`. | true | false |
| `content[].blockedBy` | Dependency list for tasks blocking this task. | Required array on task rows; count 245; samples are empty arrays. | true | false |
| `content[].blocks` | Dependency list for tasks this task blocks. | Required array on task rows; count 245; samples are empty arrays. | true | false |
| `content[].description` | Detailed task instruction or expected result. | Required string on task rows; count 245; max length 276; samples describe dependency graph parsing, whole-graph drivers, deterministic graph building, and adding a `Gpt` reading-model variant. | true | false |
| `content[].id` | Task row identifier. | Required string on task rows; count 245; max length 1; samples include `1` and `6`. | true | false |
| `content[].status` | Task status. | Required string on task rows; count 245; max length 11; samples include `completed` and `in_progress`. | true | false |
| `content[].subject` | Task subject used as the primary reminder preview. | Required string on task rows; count 245; max length 57; samples include `Step 1 - Parse dependency graph`, `Build resumable whole-graph naming driver`, `Build deterministic dependency graph`, and `Add Gpt variant to ReadingModel enum`. | true | true |
| `itemCount` | Reminder task count. | Required number; observed in all 1,045 items; samples include `0`, `3`, `4`, `5`, and `7`. | true | false |
| `type` | Attachment subtype discriminator. | Required constant string `task_reminder`. | false | false |

## Derived Car Form Content

| Field | Source Field | Contents |
| --- | --- | --- |
| Content | `content` | Reminder task array. |
| Task | `content[]` | Individual reminder task object. |
| Active Form | `content[].activeForm` | Current-action wording for the task. |
| Blocked By | `content[].blockedBy` | Dependency list for tasks blocking this task. |
| Blocks | `content[].blocks` | Dependency list for tasks this task blocks. |
| Description | `content[].description` | Detailed task instruction or expected result. |
| ID | `content[].id` | Task row identifier. |
| Status | `content[].status` | Task status. |
| Subject | `content[].subject` | Task subject. |
| Item Count | `itemCount` | Reminder task count. |

## Message Navigation Item Design

```text
Attachment / Task Reminder ............................................. 05:14:03
Step 1 - Parse dependency graph | completed | Parsing dependency graph
```

Use the attachment-teal tone and render both category levels as full badges. The first line keeps `Attachment / Task Reminder` on the left and the timestamp on the right; the second line starts with `content[].subject`, then adds `content[].status` and `content[].activeForm` when a populated `content[]` task is present. For empty reminders, show `No reminders (0 items)`.

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [Task Reminder]  05:14:03  agent/path        [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Reminder Summary                                                               |
| +----------------+---------------------------------------------------------+   |
| | Item Count     | 5                                                       |   |
| | Type           | task_reminder                                           |   |
| +----------------+---------------------------------------------------------+   |
|                                                                                |
| Tasks                                                                          |
| +------------------------------------------------------------------------------+
| | content[]                                                                    |
| | +----+-----------------------------------+-------------+-------------------+ |
| | | ID | Subject                           | Status      | Active Form       | |
| | +----+-----------------------------------+-------------+-------------------+ |
| | | 1  | Step 1 - Parse dependency graph   | completed   | Parsing dependency| |
| | |    |                                   |             | graph             | |
| | +----+-----------------------------------+-------------+-------------------+ |
| | | Description | Babel-parse all 5,738 modules; extract internal dep edges, | |
| | |             | local symbol tables, shape counters. Output graph.json +  | |
| | |             | symbols.json.                                             | |
| | | Blocks      | []                                                        | |
| | | Blocked By  | []                                                        | |
| | +-------------+-----------------------------------------------------------+ |
| +------------------------------------------------------------------------------+
|                                                                                |
| Empty State                                                                    |
| +----------------+---------------------------------------------------------+   |
| | Content        | No reminders                                           |   |
| | Item Count     | 0                                                       |   |
| +----------------+---------------------------------------------------------+   |
+--------------------------------------------------------------------------------+
```

Render `content[]` as a nested table because it is a repeated task array. Keep the task row compact with `id`, `subject`, `status`, and `activeForm`, then expand `description`, `blocks`, and `blockedBy` underneath the row so long task text and dependency arrays remain attached to the same task.
