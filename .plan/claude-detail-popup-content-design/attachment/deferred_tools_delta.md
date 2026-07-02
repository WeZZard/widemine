# Detail Popup Content Design - Attachment / Deferred Tools Delta

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Added Lines | `addedLines` | Holds the array envelope for line-oriented deferred tool additions. | Array of strings; observed up to 170 items; item values appear at `addedLines[]`. | true |
| Added Lines Item | `addedLines[]` | Carries each line-oriented deferred tool addition. | String items; observed max length 70; examples include `CronCreate`, `EnterWorktree`, and `ListMcpResourcesTool`. | true |
| Added Names | `addedNames` | Holds the array envelope for newly added deferred tool names. | Array of strings; observed up to 170 items; item values appear at `addedNames[]`. | true |
| Added Names Item | `addedNames[]` | Carries each newly added deferred tool name. | String items; observed max length 70; examples include `CronCreate`, `EnterWorktree`, and `mcp__chrome-devtools__click`. | true |
| Pending MCP Servers | `pendingMcpServers` | Holds the array envelope for MCP server names still pending while the tool delta is applied. | Array of strings; observed up to 6 items; item values appear at `pendingMcpServers[]`. | true |
| Pending MCP Servers Item | `pendingMcpServers[]` | Carries each pending MCP server name connected to the delta. | String items; observed max length 39; examples include `chrome-devtools`, `claude.ai Cloudflare Developer Platform`, and `claude.ai Notion`. | true |
| Readded Names | `readdedNames` | Holds the array envelope for deferred tool names restored after removal. | Array of strings; observed up to 88 items; item values appear at `readdedNames[]` when non-empty. | true |
| Readded Names Item | `readdedNames[]` | Carries each restored deferred tool name. | String items; observed max length 70; example includes `ListMcpResourcesTool`. | true |
| Removed Names | `removedNames` | Holds the array envelope for deferred tool names removed by the delta. | Array of strings; observed up to 114 items; item values appear at `removedNames[]` when non-empty. | true |
| Removed Names Item | `removedNames[]` | Carries each removed deferred tool name. | String items; observed max length 70; examples include `ListMcpResourcesTool`, `mcp__chrome-devtools__click`, and `mcp__chrome-devtools__take_memory_snapshot`. | true |
| Type | `type` | Raw attachment discriminator used for routing. | String; observed value is `deferred_tools_delta`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Added Lines | `addedLines` | Direct array from `addedLines`; item rows come from `addedLines[]`. | Render as a nested one-column `Added Lines` group; empty array renders `None`. |
| Added Lines Item | `addedLines[]` | Each string item in `addedLines`. | Render inside the `Added Lines` group under `Item`; never as an unrelated top-level row. |
| Added Names | `addedNames` | Direct array from `addedNames`; item rows come from `addedNames[]`. | Render as a nested one-column `Added Names` group; empty array renders `None`. |
| Added Names Item | `addedNames[]` | Each string item in `addedNames`. | Render inside the `Added Names` group under `Item`; never as an unrelated top-level row. |
| Pending MCP Servers | `pendingMcpServers` | Direct array from `pendingMcpServers`; item rows come from `pendingMcpServers[]`. | Render as a nested one-column `Pending MCP Servers` group; empty array renders `None`. |
| Pending MCP Servers Item | `pendingMcpServers[]` | Each string item in `pendingMcpServers`. | Render inside the `Pending MCP Servers` group under `Item`; never as an unrelated top-level row. |
| Readded Names | `readdedNames` | Direct array from `readdedNames`; item rows come from `readdedNames[]`. | Render as a nested one-column `Readded Names` group; empty array renders `None`. |
| Readded Names Item | `readdedNames[]` | Each string item in `readdedNames`. | Render inside the `Readded Names` group under `Item`; never as an unrelated top-level row. |
| Removed Names | `removedNames` | Direct array from `removedNames`; item rows come from `removedNames[]`. | Render as a nested one-column `Removed Names` group; empty array renders `None`. |
| Removed Names Item | `removedNames[]` | Each string item in `removedNames`. | Render inside the `Removed Names` group under `Item`; never as an unrelated top-level row. |

## Card Design

```text
+----------------------------------------------------------------------------+
| [Attachment] [Deferred Tools Delta]                              [pin] [x] |
+----------------------------------------------------------------------------+
|                         Content | Metadata | Raw                           |
+----------------------------------------------------------------------------+
| Added Lines                                                                |
|   | Item                                                                 | |
|   | CronCreate                                                           | |
|   | EnterWorktree                                                        | |
|   | ...                                                                  | |
| Added Names                                                                |
|   | Item                                                                 | |
|   | CronCreate                                                           | |
|   | mcp__chrome-devtools__click                                          | |
|   | ...                                                                  | |
| Pending MCP Servers                                                        |
|   | Item                                                                 | |
|   | chrome-devtools                                                      | |
|   | claude.ai Notion                                                     | |
| Readded Names                                                              |
|   | Item                                                                 | |
|   | ListMcpResourcesTool                                                 | |
|   | ...                                                                  | |
| Removed Names                                                              |
|   | Item                                                                 | |
|   | ListMcpResourcesTool                                                 | |
|   | mcp__chrome-devtools__click                                          | |
|   | ...                                                                  | |
+----------------------------------------------------------------------------+
```
