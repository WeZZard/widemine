# Detail Popup Content Design - Agent Name / Raw Event

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Agent Name | `agentName` | Identifies the named agent for the event. | Required string; examples include `reddit-demand-product-driver`, `reddit-driven-product-discovery`, and `observability-milestone-two`. | true |
| Session ID | `sessionId` | Correlates the event with its source session. | Required UUID string. | false |
| Type | `type` | Routes the event to its top-level message kind. | Required constant string `agent-name`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Agent Name | `agentName` | Direct value from `agentName`. | Single-line text preserving exact spelling, casing, and separators. |

## Card Design

```text
+--------------------------------------------------------------------+
| [Agent Name] [Raw Event]                                 [pin] [x] |
+--------------------------------------------------------------------+
|                      Content | Metadata | Raw                      |
+--------------------------------------------------------------------+
| Agent Name                                           <agentName>   |
+--------------------------------------------------------------------+
```
