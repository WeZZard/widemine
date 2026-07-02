# Attachment / Auto Mode

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `type` | Attachment subtype and visible mode transition value. | Required constant string `auto_mode`; rendered as the Auto Mode badge and fallback preview. | true | true |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Type | `auto_mode` |

## Message Navigation Item Design

```text
Attachment / Auto Mode ............................................... 14:32:07
Type: auto_mode
```

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Attachment / Auto Mode ............................................. 14:32:07 |
| agent/path                                                [Raw] [Copy JSON]    |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Mode Change                                                                    |
| +------------+-------------------------------------------------------------+   |
| | Field      | Value                                                       |   |
| +------------+-------------------------------------------------------------+   |
| | Type       | auto_mode                                                   |   |
| +------------+-------------------------------------------------------------+   |
|                                                                                |
| Raw button opens formatted raw JSON for this timeline item.                    |
| Copy JSON copies the raw payload.                                              |
+--------------------------------------------------------------------------------+
```
