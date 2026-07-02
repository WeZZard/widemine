# Attachment / Date Change

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `newDate` | Date value announced by the date-change attachment. | Required ISO date string; observed in all 38 items; samples include `2026-06-14`, `2026-06-16`, `2026-06-18`, and `2026-06-22`. | true | true |
| `type` | Attachment subtype discriminator used for routing and the Date Change badge. | Required constant string `date_change`. | false | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| New Date | Value from `newDate`. |

## Message Navigation Item Design

```text
Attachment / Date Change .............................................. 14:32:07
New Date: 2026-06-14
```

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Attachment / Date Change ............................................ 14:32:07 |
| agent/path                                                [Raw] [Copy JSON]    |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Date Change                                                                    |
| +------------+-------------------------------------------------------------+   |
| | Field      | Value                                                       |   |
| +------------+-------------------------------------------------------------+   |
| | New Date   | 2026-06-14                                                  |   |
| +------------+-------------------------------------------------------------+   |
+--------------------------------------------------------------------------------+
```
