# Attachment / Auto Mode Exit Waterfall Surface Design

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `type` | Attachment subtype and visible mode transition value. | Required constant string `auto_mode_exit`; rendered as the Auto Mode Exit badge and fallback preview. | true | true |

## Derived Car Form Content

| Form Field | Source Field | Control | Contents |
| --- | --- | --- | --- |
| Type | `type` | Compact scalar | Required constant string `auto_mode_exit`. |

## Message Navigation Item Design

```text
+--------------------------------------------------------------------------------+
| o  [Attachment] [Auto Mode Exit]  14:32:07  Type: auto_mode_exit               |
+--------------------------------------------------------------------------------+
  activity dot   full badges                  timestamp   first meaningful line
  tone: attachment-teal; use the same full badge style for both category levels

Preview rules:
- Use `type` as the first meaningful content line.
- Render the preview as "Type: auto_mode_exit".
- If `type` is unavailable, fall back to "Auto mode exited".
```

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [Auto Mode Exit]  14:32:07  agent/path       [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
|  Mode Change                                                                   |
|  +----------------+---------------------------------------------------------+  |
|  | Type           | auto_mode_exit                                          |  |
|  +----------------+---------------------------------------------------------+  |
|                                                                                |
|  Raw button opens formatted raw JSON for this timeline item.                   |
|  Copy JSON copies the raw payload. Use message typography and compact field    |
|  spacing for this single-field mode transition.                                |
+--------------------------------------------------------------------------------+
```
