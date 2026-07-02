# Attachment / Task Status

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `deltaSummary` | Task progress or delta summary when present. | Required nullable field; observed in 6 messages; sampled value is `null`. | true | false |
| `description` | Human-readable task description used as the primary task-status summary. | Required string; observed in 6 messages; max length 28; samples include `Implement engine-loop-state` and `Resolve audit remove-footers`. | true | true |
| `outputFilePath` | Output file path for the completed task result. | Required string; observed in 6 messages; max length 155; samples are task output paths under `/private/tmp/claude-501/.../tasks/*.output`. | true | false |
| `status` | Task completion status. | Required string; observed in 6 messages; max length 9; sampled value is `completed`. | true | false |
| `taskId` | Task identifier for the status target. | Required string; observed in 6 messages; max length 17; samples include `af0f7940a364ab246` and `a2684d0ee0dd0c909`. | true | false |
| `taskType` | Task execution type for the status target. | Required string; observed in 6 messages; max length 11; sampled value is `local_agent`. | true | false |
| `type` | Attachment subtype discriminator. | Required constant string `task_status`. | false | false |

## Derived Car Form Content

| Field | Source Field | Contents |
| --- | --- | --- |
| Delta Summary | `deltaSummary` | Task progress or delta summary. |
| Description | `description` | Human-readable task description. |
| Output File Path | `outputFilePath` | Completed task output file path. |
| Status | `status` | Task completion status. |
| Task ID | `taskId` | Task identifier. |
| Task Type | `taskType` | Task execution type. |

## Message Navigation Item Design

```text
Attachment / Task Status ............................................... 05:14:03
Implement engine-loop-state | completed | local_agent af0f7940a364ab246
```

Use the attachment-teal tone and render both category levels as full badges. The first line keeps `Attachment / Task Status` on the left and right-aligns the timestamp. The second line starts with `description`, then appends `status`, `taskType`, and `taskId`; include `deltaSummary` after status when it is non-null.

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [Task Status]  05:14:03  agent/path          [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Task Status                                                                    |
| +------------------+---------------------------------------------------------+ |
| | Description      | Implement engine-loop-state                            | |
| | Status           | completed                                               | |
| | Task Type        | local_agent                                             | |
| | Task ID          | af0f7940a364ab246                                       | |
| | Delta Summary    | null                                                    | |
| | Output File Path | /private/tmp/claude-501/.../tasks/af0f7940a364ab246... | |
| +------------------+---------------------------------------------------------+ |
|                                                                                |
| Output                                                                         |
| +------------------+---------------------------------------------------------+ |
| | Output File Path | /private/tmp/claude-501/.../tasks/af0f7940a364ab246... | |
| +------------------+---------------------------------------------------------+ |
|                                                                                |
| Raw actions: Raw opens formatted raw JSON; Copy JSON copies the raw payload.   |
+--------------------------------------------------------------------------------+
```

No nested array table is needed for this subtype because the observed shape is flat. Keep the status fields together in the primary content form, and repeat `outputFilePath` in the output area only when the card provides a link or open-file affordance.
