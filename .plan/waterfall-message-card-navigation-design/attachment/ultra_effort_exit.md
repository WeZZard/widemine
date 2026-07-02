# Attachment / Ultra Effort Exit

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `type` | Identifies the attachment subtype and visible Ultra Effort exit transition for badges, routing, and fallback preview text. | Required constant string `ultra_effort_exit`; observed in 1 message. | true | true |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Type | `ultra_effort_exit` |

## Message Navigation Item Design

```text
Attachment / Ultra Effort Exit ........................................ 14:32:07
Type: ultra_effort_exit
```

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [Ultra Effort Exit]  14:32:07  agent/path    [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
|  Mode Change                                                                   |
|  +-------+------------------------------------------------------------------+  |
|  | Field | Value                                                            |  |
|  +-------+------------------------------------------------------------------+  |
|  | Type  | ultra_effort_exit                                                |  |
|  +-------+------------------------------------------------------------------+  |
|                                                                                |
|  Raw button opens formatted raw JSON for this timeline item.                   |
|  Copy JSON copies the raw payload. Use message typography and compact field    |
|  spacing for this single-field mode transition.                                |
+--------------------------------------------------------------------------------+
```
