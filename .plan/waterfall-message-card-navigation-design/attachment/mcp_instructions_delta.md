# Attachment / MCP Instructions Delta

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `addedBlocks` | Added MCP instruction block array and count source. | Required array; observed in all 100 messages; max 2 items; empty in the removal-only shape. | true | false |
| `addedBlocks[]` | Individual added MCP instruction block. | String array item; 109 observed items; max length 4,863; samples include instruction blocks for `computer-use` and `cua-driver`. | true | false |
| `addedNames` | Added MCP instruction names for the positive delta result. | Required array; observed in all 100 messages; max 2 items; empty in the removal-only shape. | true | true |
| `addedNames[]` | Individual added MCP instruction name. | String array item; 109 observed items; max length 12; samples include `computer-use` and `cua-driver`. | true | false |
| `removedNames` | Removed MCP instruction names for the negative delta result. | Required array; observed in all 100 messages; max 1 item; empty in 99 messages. | true | false |
| `removedNames[]` | Individual removed MCP instruction name. | String array item; 1 observed item; max length 12; sample includes `computer-use`. | true | false |
| `type` | Attachment subtype discriminator. | Required string; constant sample `mcp_instructions_delta`. | false | false |

## Derived Car Form Content

| Field | Source Field | Contents |
| --- | --- | --- |
| Added Blocks | `addedBlocks` | Added instruction block array. |
| Added Block | `addedBlocks[]` | Added instruction block string. |
| Added Names | `addedNames` | Added instruction name array. |
| Added Name | `addedNames[]` | Added instruction name string. |
| Removed Names | `removedNames` | Removed instruction name array. |
| Removed Name | `removedNames[]` | Removed instruction name string. |

## Message Navigation Item Design

```text
Attachment / MCP Instructions Delta .................................... 14:32:07
Added names: 2 | Added blocks: 2 | Removed names: 0
```

Use the attachment-teal tone and render both category levels as full badges where the navigation component supports badges. The second line is a compact count summary from `addedNames`, `addedBlocks`, and `removedNames`; keep additions and removals separate so a removal-only delta renders as `Added names: 0 | Added blocks: 0 | Removed names: 1`.

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [MCP Instructions Delta]  14:32:07  agent/path [Raw] [Copy JSON]|
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Delta Summary                                                                  |
| +----------------+---------------------------------------------------------+   |
| | Added Names    | 2                                                       |   |
| | Added Blocks   | 2                                                       |   |
| | Removed Names  | 0                                                       |   |
| | Type           | mcp_instructions_delta                                  |   |
| +----------------+---------------------------------------------------------+   |
|                                                                                |
| Added                                                                          |
| +----+----------------+---------------------------------------------------+   |
| | #  | addedNames[]   | addedBlocks[]                                     |   |
| +----+----------------+---------------------------------------------------+   |
| | 1  | computer-use   | ## computer-use You have a computer-use MCP...    |   |
| | 2  | cua-driver     | ## cua-driver cua-driver: cross-platform...      |   |
| +----+----------------+---------------------------------------------------+   |
|                                                                                |
| Removed                                                                        |
| +----+----------------+                                                   |   |
| | #  | removedNames[] |                                                   |   |
| +----+----------------+                                                   |   |
| | -  | none           |                                                   |   |
| +----+----------------+                                                   |   |
|                                                                                |
| Removal-Only Delta                                                             |
| +----+----------------+                                                   |   |
| | #  | removedNames[] |                                                   |   |
| +----+----------------+                                                   |   |
| | 1  | computer-use   |                                                   |   |
| +----+----------------+                                                   |   |
+--------------------------------------------------------------------------------+
```

Render `addedNames[]` and `addedBlocks[]` together in a nested Added table because they describe the same positive delta entries. Render `removedNames[]` as its own nested Removed table, including an explicit empty state for common add-only deltas and a populated row for the removal-only shape. Wrap long `addedBlocks[]` text in message typography and keep the Raw button available for the complete instruction block.
