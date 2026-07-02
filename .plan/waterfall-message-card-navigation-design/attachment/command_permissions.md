# Attachment / Command Permissions

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `allowedTools` | Granted tool list for the command permission decision. | Required array; observed in 233 messages; empty in 218 messages; populated in 15 messages; max 4 items. | true | true |
| `allowedTools[]` | Individual granted tool specifier. | String array item when present; 41 observed items; max length 14; samples include `Read`, `Bash(linear:*)`, and `Bash`. | true | false |
| `type` | Attachment subtype discriminator. | Required string; constant sample `command_permissions`. | false | false |

## Derived Car Form Content

| Field | Source Field | Contents |
| --- | --- | --- |
| Allowed Tools | `allowedTools` | Allowed tools array. |
| Allowed Tool | `allowedTools[]` | Allowed tool string. |

## Message Navigation Item Design

```text
Attachment / Command Permissions ........................................ 14:32:07
Allowed tools: 3 - Read, Bash(linear:*), Bash
```

Use the attachment-teal tone and render both category levels as full badges. The second line is count-led from `allowedTools`; when the array is empty, render `Allowed tools: 0 - none` so the item reads as a deliberate permission state.

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [Command Permissions]  14:32:07  agent/path  [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Permission Decision                                                            |
| +----------------+----------------------------------------------------------+  |
| | Allowed Tools  | 3                                                        |  |
| | Type           | command_permissions                                      |  |
| +----------------+----------------------------------------------------------+  |
|                                                                                |
| Allowed Tools                                                                  |
| +----+-------------------+                                                     |
| | #  | allowedTools[]    |                                                     |
| +----+-------------------+                                                     |
| | 1  | Read              |                                                     |
| | 2  | Bash(linear:*)    |                                                     |
| | 3  | Bash              |                                                     |
| +----+-------------------+                                                     |
|                                                                                |
| Empty Allowed Tools                                                            |
| +----+-------------------+                                                     |
| | #  | allowedTools[]    |                                                     |
| +----+-------------------+                                                     |
| | -  | none              |                                                     |
| +----+-------------------+                                                     |
+--------------------------------------------------------------------------------+
```

Render `allowedTools[]` as the nested array table because the flattened field carries repeated values. Keep `allowedTools` visible as the summary count, and keep the empty-array state explicit instead of omitting the section.
