# Detail Popup Content Design - Last Prompt / Raw Event

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Last Prompt | `lastPrompt` | Carries the recorded end-user prompt when the raw event includes one. | String prompt text; present in 3,500 observed messages and absent from 123 observed messages. | true |
| Leaf UUID | `leafUuid` | Correlates the event with a transcript leaf. | UUID string in all observed messages. | false |
| Session ID | `sessionId` | Correlates the event with its source session. | UUID string in all observed messages. | false |
| Type | `type` | Supplies the routing category already represented by the popup titlebar. | Constant string value `last-prompt`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Last Prompt | `lastPrompt` | Raw `lastPrompt` string when present; otherwise no derived row content is shown for that field. | Wrapped multiline text with preserved line breaks. |

## Card Design

```text
+------------------------------------------------------------------------------+
| [Last Prompt] [Raw Event]                                      [pin] [x]      |
+------------------------------------------------------------------------------+
|                           Content | Metadata | Raw                            |
+------------------------------------------------------------------------------+
| Last Prompt                                                                  |
| <lastPrompt value, wrapped with preserved line breaks>                        |
+------------------------------------------------------------------------------+
```
