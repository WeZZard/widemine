## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| condition | `condition` | Defines the goal condition being evaluated. | String goal statement; observed in both shapes. | true |
| met | `met` | Reports whether the goal condition has been met. | Boolean result; observed as `false` in sentinel status and `true` in completed status. | true |
| sentinel | `sentinel` | Marks a sentinel status attachment shape. | Boolean marker; observed only in the sentinel shape. | false |
| type | `type` | Routes the attachment payload to the goal-status renderer. | String value `goal_status`; category identity belongs in the popup titlebar. | false |
| durationMs | `durationMs` | Supports the completed goal result with elapsed time. | Numeric duration in milliseconds; observed only in completed status. | true |
| iterations | `iterations` | Supports the status result with iteration count. | Numeric count; observed only in completed status. | true |
| reason | `reason` | Explains the evidence and outcome behind the goal result. | String explanation; observed only in completed status. | true |
| tokens | `tokens` | Supports the status result with token usage. | Numeric token count; observed only in completed status. | true |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Condition | `condition` | Direct value from `condition`. | Full-width multiline text field; wrap long text and preserve inline code formatting. |
| Met | `met` | Direct value from `met`. | Boolean field rendered as `true` or `false`. |
| Duration Ms | `durationMs` | Direct value from `durationMs` when present. | Numeric field with `ms` unit; omit the row when absent. |
| Iterations | `iterations` | Direct value from `iterations` when present. | Numeric field; omit the row when absent. |
| Reason | `reason` | Direct value from `reason` when present. | Full-width multiline text field; wrap long explanations and preserve inline code formatting. |
| Tokens | `tokens` | Direct value from `tokens` when present. | Numeric field; omit the row when absent. |

## Card Design

```text
+------------------------------------------------------------------------------+
| [Attachment] [Goal Status]                                           [pin] [x] |
+------------------------------------------------------------------------------+
|                         Content | Metadata | Raw                              |
+------------------------------------------------------------------------------+
| Condition                                                                    |
| <condition>                                                                  |
|                                                                              |
| Met            <met>                                                          |
| Duration Ms    <durationMs> ms                                                |
| Iterations     <iterations>                                                   |
|                                                                              |
| Reason                                                                       |
| <reason>                                                                     |
|                                                                              |
| Tokens         <tokens>                                                       |
+------------------------------------------------------------------------------+
```
