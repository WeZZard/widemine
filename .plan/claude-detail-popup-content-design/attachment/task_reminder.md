# Detail Popup Content Design - Attachment / Task Reminder

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Content | `content` | Holds the reminder item array that forms the visible task reminder body. | Array; 1022 observed payloads, with 965 empty arrays and populated arrays up to 7 items. | true |
| Content Item | `content[]` | Represents each reminder object in the repeated task reminder list. | Object; 225 observed items across populated reminder arrays. | true |
| Active Form | `content[].activeForm` | Shows the current action phrase for each reminder item. | String; examples include `Parsing dependency graph`, `Building whole-graph driver`, `Building dependency graph`, and `Adding Gpt reading model variant`; observed max length 37. | true |
| Blocked By | `content[].blockedBy` | Lists prerequisite reminder IDs that block the item. | Array; present on each populated reminder item. | true |
| Blocks | `content[].blocks` | Lists downstream reminder IDs blocked by the item. | Array; present on each populated reminder item. | true |
| Description | `content[].description` | Provides the detailed task reminder body for each item. | String; examples describe parsing dependency graphs, building naming drivers, and adding a `Gpt` reading model variant; observed max length 276. | true |
| ID | `content[].id` | Identifies each reminder item and supports `blockedBy` and `blocks` references. | String; samples include `1` and `6`; observed max length 1. | true |
| Status | `content[].status` | Shows the recorded task state for each reminder item. | String; samples include `completed` and `in_progress`; observed max length 11. | true |
| Subject | `content[].subject` | Shows the primary subject line for each reminder item. | String; examples include `Step 1 - Parse dependency graph`, `Build resumable whole-graph naming driver`, `Build deterministic dependency graph`, and `Add Gpt variant to ReadingModel enum`; observed max length 57. | true |
| Item Count | `itemCount` | States how many reminder items are present, including the empty-list case. | Number; samples include `0`, `5`, `3`, `4`, and `7`. | true |
| Type | `type` | Routes this attachment payload; category identity is already shown in the popup titlebar. | String; observed value is `task_reminder`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Item Count | `itemCount` | Direct number from `itemCount`. | Render as a compact numeric row before the nested `Content` group. |
| Content | `content` | Direct array from `content`; item rows come from `content[]`. | Render as a nested `Content` group; when empty, render `None` inside the group rather than creating item rows. |
| Content Item | `content[]` | Each object in `content` in source order. | Render as one row in the nested `Content` table using the child fields below. |
| Active Form | `content[].activeForm` | Direct value from each `content[]` item. | Render inside the `Content` group under `Active Form`; wrap long values within the cell. |
| Blocked By | `content[].blockedBy` | Direct array from each `content[]` item. | Render inside the `Content` group under `Blocked By` as compact ID tokens; show `[]` when empty. |
| Blocks | `content[].blocks` | Direct array from each `content[]` item. | Render inside the `Content` group under `Blocks` as compact ID tokens; show `[]` when empty. |
| Description | `content[].description` | Direct value from each `content[]` item. | Render inside the `Content` group under `Description` as wrapped text with long content constrained to the row. |
| ID | `content[].id` | Direct value from each `content[]` item. | Render inside the `Content` group under `ID` as a compact identifier. |
| Status | `content[].status` | Direct value from each `content[]` item. | Render inside the `Content` group under `Status` as a compact status value. |
| Subject | `content[].subject` | Direct value from each `content[]` item. | Render inside the `Content` group under `Subject` as the leading item summary. |

## Card Design

```text
+---------------------------------------------------------------------------------------------+
| [Attachment] [Task Reminder]                                                      [pin] [x] |
+---------------------------------------------------------------------------------------------+
|                                       Content | Metadata | Raw                              |
+---------------------------------------------------------------------------------------------+
| Item Count   5                                                                              |
| Content                                                                                     |
|   +----+---------------+----------------+-----------+-------------+------------+--------+   |
|   | ID | Subject       | Description    | Status    | Active Form | Blocked By | Blocks |   |
|   +----+---------------+----------------+-----------+-------------+------------+--------+   |
|   | 1  | Step 1...     | Babel-parse... | completed | Parsing...  | []         | []     |   |
|   | 6  | Build driver  | Seed map...    | in_prog.. | Building... | [1]        | []     |   |
|   +----+---------------+----------------+-----------+-------------+------------+--------+   |
+---------------------------------------------------------------------------------------------+
```
