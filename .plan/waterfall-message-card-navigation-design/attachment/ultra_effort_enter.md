# Attachment / Ultra Effort Enter

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `type` | Identifies the attachment subtype and Ultra Effort enter transition for badges, routing, and fallback preview text. | Required constant string `ultra_effort_enter`; observed in 6 messages. | true | true |
| `reminderType` | Records the reminder variant attached to the Ultra Effort enter transition. | Required string observed as `full` or `sparse`; observed in 6 messages. | true | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Type | `ultra_effort_enter` |
| Reminder Type | `full` or `sparse` |

## Message Navigation Item Design

```text
Attachment / Ultra Effort Enter ....................................... 14:32:07
Type: ultra_effort_enter
```

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| o  Attachment / Ultra Effort Enter  main ............................ 14:32:07 |
|                                                         [Raw] [Copy JSON]      |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
|  Mode Change                                                                   |
|  +---------------+----------------------------------------------------------+  |
|  | Field         | Value                                                    |  |
|  +---------------+----------------------------------------------------------+  |
|  | Type          | ultra_effort_enter                                       |  |
|  | Reminder Type | full                                                     |  |
|  +---------------+----------------------------------------------------------+  |
|                                                                                |
|  Raw button opens formatted raw JSON for this timeline item.                   |
|  Copy JSON copies the raw payload.                                             |
+--------------------------------------------------------------------------------+
```
