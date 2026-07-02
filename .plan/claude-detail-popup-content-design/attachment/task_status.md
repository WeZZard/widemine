# Detail Popup Content Design - Attachment / Task Status

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Delta Summary | `deltaSummary` | Carries task-result summary text when the update includes one. | Null in all 6 observed samples. | true |
| Description | `description` | Names the task goal whose status is being reported. | String task descriptions such as `Implement engine-loop-state` and `Resolve audit remove-footers`. | true |
| Output File Path | `outputFilePath` | Stores the internal task output artifact path for trace review. | Temporary filesystem paths under task output storage. | false |
| Status | `status` | Reports the current or final state of the task. | String status value; observed value is `completed`. | true |
| Task ID | `taskId` | Identifies the task instance whose status is being reported. | String task identifiers such as `af0f7940a364ab246` and `a2684d0ee0dd0c909`. | true |
| Task Type | `taskType` | Identifies the executor class for the reported task. | String task type; observed value is `local_agent`. | true |
| Type | `type` | Routes the attachment payload as a task-status record. | String routing value; observed value is `task_status`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Status | `status` | Read directly from `status`. | Compact status text. |
| Description | `description` | Read directly from `description`. | Plain text value; wrap within the row. |
| Delta Summary | `deltaSummary` | Read directly from `deltaSummary`. | Multiline text row when non-null; omit the row when null. |
| Task ID | `taskId` | Read directly from `taskId`. | Monospace copyable identifier. |
| Task Type | `taskType` | Read directly from `taskType`. | Compact text value. |

## Card Design

```text
+----------------------------------------------------------------+
| [Attachment] [Task Status]                            [pin] [x] |
+----------------------------------------------------------------+
|                    Content | Metadata | Raw                    |
+----------------------------------------------------------------+
| Status       <status>                                          |
| Description  <description>                                     |
| Delta Summary <deltaSummary when non-null>                     |
| Task ID      <taskId>                                          |
| Task Type    <taskType>                                        |
+----------------------------------------------------------------+
```
