# Detail Popup Content Design - System / Stop Hook Summary

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| CWD | `cwd` | Provides working-directory context for locating the transcript event. | Types: string. Count: 1355. Max length: 135. | false |
| Entrypoint | `entrypoint` | Records the client entrypoint that produced the transcript event. | Types: string. Count: 1355. Max length: 13. | false |
| Git Branch | `gitBranch` | Records repository branch context for the event. | Types: string. Count: 1355. Max length: 43. | false |
| Has Output | `hasOutput` | Indicates whether stop hook processing emitted output. | Types: bool. Count: 1355. | true |
| Hook Additional Context | `hookAdditionalContext` | Array container for additional stop-hook context entries. | Types: array. Count: 1089. Max items: 1. | false |
| Hook Additional Context | `hookAdditionalContext[]` | Carries hook-provided context attached to the stop summary. | Types: string. Count: 1. Max length: 751. | true |
| Hook Count | `hookCount` | Reports how many stop hooks were evaluated. | Types: number. Count: 1355. | true |
| Hook Errors | `hookErrors` | Array container for hook error or status entries. | Types: array. Count: 1355. Max items: 1. | false |
| Hook Errors | `hookErrors[]` | Carries hook failure or loop-status text visible to the user. | Types: string. Count: 14. Max length: 101. | true |
| Hook Infos | `hookInfos` | Array container for individual hook run records. | Types: array. Count: 1355. Max items: 3. | false |
| Hook Infos | `hookInfos[]` | Object container for one hook run record. | Types: object. Count: 2520. | false |
| Command | `hookInfos[].command` | Identifies the hook command that ran. | Types: string. Count: 2520. Max length: 265. | true |
| Duration Ms | `hookInfos[].durationMs` | Records how long the hook command ran. | Types: number. Count: 2519. | true |
| Prompt Text | `hookInfos[].promptText` | Carries recorded hook prompt text when present. | Types: string. Count: 1. Max length: 265. | true |
| Is Sidechain | `isSidechain` | Records sidechain routing context for the transcript event. | Types: bool. Count: 1355. | false |
| Level | `level` | Records the stop hook summary severity level. | Types: string. Count: 1355. Max length: 10. | true |
| Parent UUID | `parentUuid` | Links this event to its parent transcript record. | Types: string. Count: 1355. Max length: 36. | false |
| Prevented Continuation | `preventedContinuation` | Indicates whether hook processing stopped continuation. | Types: bool. Count: 1355. | true |
| Session ID | `sessionId` | Links this event to a transcript session. | Types: string. Count: 1355. Max length: 36. | false |
| Slug | `slug` | Records scan or session slug metadata. | Types: string. Count: 1006. Max length: 53. | false |
| Stop Reason | `stopReason` | Records the stop reason attached to the hook summary. | Types: string. Count: 1355. | true |
| Subtype | `subtype` | Supports routing and titlebar identity. | Types: string. Count: 1355. Max length: 17. | false |
| Timestamp | `timestamp` | Records event time for sorting and metadata display. | Types: string. Count: 1355. Max length: 24. | false |
| Tool Use ID | `toolUseID` | Links this event to related tool-use records. | Types: string. Count: 1355. Max length: 36. | false |
| Type | `type` | Supports routing and titlebar identity. | Types: string. Count: 1355. Max length: 6. | false |
| User Type | `userType` | Records transcript user category metadata. | Types: string. Count: 1355. Max length: 8. | false |
| UUID | `uuid` | Identifies the transcript record. | Types: string. Count: 1355. Max length: 36. | false |
| Version | `version` | Records producer version metadata. | Types: string. Count: 1355. Max length: 7. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Has Output | `hasOutput` | Direct value from `hasOutput`. | Render as yes or no. |
| Hook Additional Context | `hookAdditionalContext[]` | Values from each `hookAdditionalContext[]` entry. | Render as a nested list with wrapped text and preserved line breaks; use the section scroll area instead of expand/collapse controls. |
| Hook Count | `hookCount` | Direct value from `hookCount`. | Render as an integer. |
| Hook Errors | `hookErrors[]` | Values from each `hookErrors[]` entry. | Render as a nested list with error styling, wrapped text, and preserved line breaks; use the section scroll area instead of expand/collapse controls. |
| Command | `hookInfos[].command` | Value from each `hookInfos[]` row. | Render as monospace command text inside the Hook Infos nested table. |
| Duration Ms | `hookInfos[].durationMs` | Value from each `hookInfos[]` row. | Render as milliseconds inside the Hook Infos nested table. |
| Prompt Text | `hookInfos[].promptText` | Optional value from each `hookInfos[]` row. | Render as wrapped text with preserved line breaks inside the Hook Infos nested table. |
| Level | `level` | Direct value from `level`. | Render as a compact scalar value. |
| Prevented Continuation | `preventedContinuation` | Direct value from `preventedContinuation`. | Render as yes or no. |
| Stop Reason | `stopReason` | Direct value from `stopReason`. | Render as text; show `empty` for blank values. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [System] [Stop Hook Summary]                                   [pin] [x] |
+--------------------------------------------------------------------------+
|                         Content | Metadata | Raw                         |
+--------------------------------------------------------------------------+
| Has Output             <hasOutput>                                       |
| Hook Count             <hookCount>                                       |
| Level                  <level>                                           |
| Prevented Continuation <preventedContinuation>                           |
| Stop Reason            <stopReason or empty>                             |
|                                                                          |
| Hook Additional Context                                                  |
|   +----------------------------------------------------------------------+ |
|   | Hook Additional Context                                             | |
|   | <hookAdditionalContext[]>                                           | |
|   +----------------------------------------------------------------------+ |
|                                                                          |
| Hook Errors                                                              |
|   +----------------------------------------------------------------------+ |
|   | Hook Errors                                                         | |
|   | <hookErrors[]>                                                      | |
|   +----------------------------------------------------------------------+ |
|                                                                          |
| Hook Infos                                                               |
|   +------------------------------+-------------+-------------------------+ |
|   | Command                      | Duration Ms | Prompt Text             | |
|   +------------------------------+-------------+-------------------------+ |
|   | <hookInfos[].command>        | <duration>  | <promptText or empty>   | |
|   +------------------------------+-------------+-------------------------+ |
+--------------------------------------------------------------------------+
```
