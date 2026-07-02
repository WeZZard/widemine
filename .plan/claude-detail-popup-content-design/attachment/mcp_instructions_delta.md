# Detail Popup Content Design - Attachment / MCP Instructions Delta

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Added Blocks | `addedBlocks` | Holds the array envelope for MCP instruction blocks added by the delta. | Array of strings; observed up to 2 items; item values appear at `addedBlocks[]`. | true |
| Added Blocks Item | `addedBlocks[]` | Carries each newly added MCP instruction block. | String items; observed max length 4863; examples begin with `## computer-use` and `## cua-driver`. | true |
| Added Names | `addedNames` | Holds the array envelope for MCP instruction names added by the delta. | Array of strings; observed up to 2 items; item values appear at `addedNames[]`. | true |
| Added Names Item | `addedNames[]` | Carries each newly added MCP instruction name. | String items; observed max length 12; examples include `computer-use` and `cua-driver`. | true |
| Removed Names | `removedNames` | Holds the array envelope for MCP instruction names removed by the delta. | Array of strings; observed up to 1 item; item values appear at `removedNames[]` when non-empty. | true |
| Removed Names Item | `removedNames[]` | Carries each removed MCP instruction name. | String items; observed max length 12; example includes `computer-use`. | true |
| Type | `type` | Raw attachment discriminator used for routing. | String; observed value is `mcp_instructions_delta`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Added Blocks | `addedBlocks` | Direct array from `addedBlocks`; item rows come from `addedBlocks[]`. | Render as a nested one-column `Added Blocks` group; empty array renders `None`. |
| Added Blocks Item | `addedBlocks[]` | Each string item in `addedBlocks`. | Render inside the `Added Blocks` group under `Item`; preserve line breaks and wrap long instruction text in a scrollable cell with no expand/collapse control. |
| Added Names | `addedNames` | Direct array from `addedNames`; item rows come from `addedNames[]`. | Render as a nested one-column `Added Names` group; empty array renders `None`. |
| Added Names Item | `addedNames[]` | Each string item in `addedNames`. | Render inside the `Added Names` group under `Item`; never as an unrelated top-level row. |
| Removed Names | `removedNames` | Direct array from `removedNames`; item rows come from `removedNames[]`. | Render as a nested one-column `Removed Names` group; empty array renders `None`. |
| Removed Names Item | `removedNames[]` | Each string item in `removedNames`. | Render inside the `Removed Names` group under `Item`; never as an unrelated top-level row. |

## Card Design

```text
+----------------------------------------------------------------------------+
| [Attachment] [MCP Instructions Delta]                            [pin] [x] |
+----------------------------------------------------------------------------+
|                         Content | Metadata | Raw                           |
+----------------------------------------------------------------------------+
| Added Blocks                                                                |
|   | Item                                                                 | |
|   | ## computer-use ...                                                 | |
|   | ## cua-driver ...                                                   | |
| Added Names                                                                 |
|   | Item                                                                 | |
|   | computer-use                                                         | |
|   | cua-driver                                                           | |
| Removed Names                                                               |
|   | Item                                                                 | |
|   | computer-use                                                         | |
|   | None                                                                 | |
+----------------------------------------------------------------------------+
```
