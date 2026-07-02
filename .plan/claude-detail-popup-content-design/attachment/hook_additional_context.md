# Detail Popup Content Design - Attachment / Hook Additional Context

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Content | `content` | Contains the hook-supplied additional context entries. | Array; observed with one string item in each sampled message. | false |
| Content Item | `content[]` | Provides each hook-supplied context entry shown in the Content tab. | String item from the content array; often instructions, diagnostics, reminders, or other hook-provided context; observed max length 7525. | true |
| Hook Event | `hookEvent` | Identifies the hook event that produced the additional context. | String such as `SessionStart`, `UserPromptSubmit`, `PostToolUseFailure`, `PostToolUse`, or `Stop`. | true |
| Hook Name | `hookName` | Identifies the configured hook name that produced the additional context. | String such as `SessionStart`, `PostToolUseFailure:WebFetch`, `PostToolUse:EnterPlanMode`, or `Stop`. | true |
| Tool Use ID | `toolUseID` | Links the hook attachment to a related tool or hook record. | String identifier such as `SessionStart`, a `hook-...` id, or a `toolu_...` id. | false |
| Type | `type` | Routes the attachment payload shape; titlebar already communicates category identity. | Constant string `hook_additional_context`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Content | `content[]` | Use each string item from `content`; show `Not provided` when the array is empty or absent. | Render as a `Content` array group with a one-column nested table; preserve line breaks in a scrollable cell with no expand/collapse control. |
| Hook Event | `hookEvent` | Use the recorded field value when present; show `Not provided` when absent. | Render as a compact labeled scalar value. |
| Hook Name | `hookName` | Use the recorded field value when present; show `Not provided` when absent. | Render as a compact labeled scalar value. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [Attachment] / [Hook Additional Context]                       [pin] [x] |
+--------------------------------------------------------------------------+
|                       Content | Metadata | Raw                           |
+--------------------------------------------------------------------------+
| Content                                                                  |
| +----------------------------------------------------------------------+ |
| | Content                                                              | |
| | <content[] item, repeated for each array entry>                      | |
| +----------------------------------------------------------------------+ |
|                                                                          |
| Hook Event             <value from hookEvent>                            |
| Hook Name              <value from hookName>                             |
+--------------------------------------------------------------------------+
```
