# Detail Popup Content Design - Attachment / Command Permissions

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Allowed Tools | `allowedTools` | Provides the command permission allow-list array, including the empty-array state when no tools are granted. | Array; observed in all shapes, empty in most records and up to 4 items when populated. | true |
| Allowed Tools Item | `allowedTools[]` | Provides each allowed tool or shell permission pattern shown to the user. | String array item; observed examples include `Read`, `Bash(linear:*)`, and `Bash`. | true |
| Type | `type` | Routes the attachment payload as a command permissions record; category identity is already shown in the popup titlebar. | String; observed value `command_permissions`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Allowed Tools | `allowedTools` | Direct array from `allowedTools`. | Render as the parent `Allowed Tools` nested form group; show an empty-state row when the array has no items. |
| Allowed Tools Item | `allowedTools[]` | Each scalar item from `allowedTools[]` in source order. | Render inside the `Allowed Tools` group as a one-column nested table of monospace permission tokens. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [Attachment] [Command Permissions]                             [pin] [x] |
+--------------------------------------------------------------------------+
|                       Content | Metadata | Raw                           |
+--------------------------------------------------------------------------+
| Allowed Tools                                                            |
|   +----------------------+                                               |
|   | Allowed Tools Item   |                                               |
|   +----------------------+                                               |
|   | Read                 |                                               |
|   | Bash(linear:*)       |                                               |
|   | Bash                 |                                               |
|   +----------------------+                                               |
+--------------------------------------------------------------------------+
```
