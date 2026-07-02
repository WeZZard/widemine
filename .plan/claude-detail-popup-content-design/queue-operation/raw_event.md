# Detail Popup Content Design - Queue Operation / Raw Event

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Content | `content` | Carries the queued raw event payload when the queue entry has visible content. | String; examples include slash commands, task notifications, MCP availability text, and user-entered text; present on the enqueue/popAll content shape. | true |
| Operation | `operation` | States the queue action performed by the raw event. | String; observed values are `enqueue`, `dequeue`, `remove`, and `popAll`. | true |
| Session ID | `sessionId` | Correlates the queue event with its source session. | UUID string present on both observed shapes. | false |
| Timestamp | `timestamp` | Places the queue event in timeline order. | ISO timestamp string present on both observed shapes. | false |
| Type | `type` | Routes the raw event to the queue-operation category. | Constant string `queue-operation`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Content | `content` | Use the raw `content` value when present. | Render as a complete wrapped multiline text block in a bounded scroll area; preserve line breaks. |
| Operation | `operation` | Use the raw `operation` value. | Render as a compact scalar value. |

## Card Design

```text
+------------------------------------------------------------------------------+
| [Queue Operation] [Raw Event]                                      [pin] [x]  |
+------------------------------------------------------------------------------+
|                           Content | Metadata | Raw                            |
+------------------------------------------------------------------------------+
| Content    <content value, wrapped with preserved line breaks when present>    |
| Operation  <operation value>                                                  |
+------------------------------------------------------------------------------+
```
