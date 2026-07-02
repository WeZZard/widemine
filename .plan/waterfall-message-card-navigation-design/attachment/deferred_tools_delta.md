# Attachment / Deferred Tools Delta

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `addedLines` | Added tool display lines for the positive delta list. | Required array; observed in all shapes; max 170 items; empty when no newly added tool lines are present. | true | false |
| `addedLines[]` | Individual added tool display line. | String; max length 70; samples include `CronCreate`, `EnterWorktree`, `mcp__chrome-devtools__click`, and `ListMcpResourcesTool`. | true | false |
| `addedNames` | Added tool names for the main delta result. | Required array; observed in all shapes; max 170 items; empty when no new tool names are present. | true | true |
| `addedNames[]` | Individual added tool name. | String; max length 70; samples include `CronCreate`, `EnterWorktree`, `mcp__chrome-devtools__click`, and `ListMcpResourcesTool`. | true | false |
| `pendingMcpServers` | Pending MCP server names associated with the delta. | Array when present; max 6 items; empty when no MCP servers are pending. | true | false |
| `pendingMcpServers[]` | Individual pending MCP server name. | String; max length 39; samples include `chrome-devtools`, `claude.ai Cloudflare Developer Platform`, and `claude.ai Notion`. | true | false |
| `readdedNames` | Re-added tool names for tools restored by the delta. | Required array; observed in all shapes; max 88 items; empty when no restored tool names are present. | true | false |
| `readdedNames[]` | Individual re-added tool name. | String; max length 70; sample includes `ListMcpResourcesTool`. | true | false |
| `removedNames` | Removed tool names for the negative delta list. | Required array; observed in all shapes; max 114 items; empty when no tool names are removed. | true | false |
| `removedNames[]` | Individual removed tool name. | String; max length 70; samples include `ListMcpResourcesTool`, `mcp__claude_ai_Google_Calendar__create_event`, and `mcp__chrome-devtools__take_memory_snapshot`. | true | false |
| `type` | Attachment subtype discriminator. | Required string; constant sample `deferred_tools_delta`. | false | false |

## Derived Car Form Content

| Field | Source Field | Contents |
| --- | --- | --- |
| Added Lines | `addedLines` | Added tool display lines. |
| Added Line | `addedLines[]` | Individual added tool display line. |
| Added Names | `addedNames` | Added tool names. |
| Added Name | `addedNames[]` | Individual added tool name. |
| Pending MCP Servers | `pendingMcpServers` | Pending MCP server names. |
| Pending MCP Server | `pendingMcpServers[]` | Individual pending MCP server name. |
| Readded Names | `readdedNames` | Re-added tool names. |
| Readded Name | `readdedNames[]` | Individual re-added tool name. |
| Removed Names | `removedNames` | Removed tool names. |
| Removed Name | `removedNames[]` | Individual removed tool name. |

## Message Navigation Item Design

```text
Attachment / Deferred Tools Delta ...................................... 14:32:07
Added names: 146 | Readded names: 0 | Removed names: 0 | Pending MCP servers: 0
```

Use the attachment-teal tone and render both category levels as full badges. The second line uses compact counts from `addedNames`, `readdedNames`, `removedNames`, and `pendingMcpServers`; keep additions and removals separate instead of collapsing them into one opaque delta label.

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [Deferred Tools Delta]  14:32:07  agent/path  [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Delta Summary                                                                  |
| +---------------------+------------------------------------------------------+ |
| | Added Names         | 146                                                  | |
| | Readded Names       | 0                                                    | |
| | Removed Names       | 0                                                    | |
| | Pending MCP Servers | 0                                                    | |
| | Type                | deferred_tools_delta                                | |
| +---------------------+------------------------------------------------------+ |
|                                                                                |
| Added                                                                          |
| +---------------------+------------------------------------------------------+ |
| | addedNames[]        | CronCreate                                           | |
| |                     | EnterWorktree                                        | |
| |                     | mcp__chrome-devtools__click                          | |
| | addedLines[]        | CronCreate                                           | |
| |                     | EnterWorktree                                        | |
| +---------------------+------------------------------------------------------+ |
|                                                                                |
| Readded                                                                        |
| +---------------------+------------------------------------------------------+ |
| | readdedNames[]      | ListMcpResourcesTool                                 | |
| +---------------------+------------------------------------------------------+ |
|                                                                                |
| Removed                                                                        |
| +---------------------+------------------------------------------------------+ |
| | removedNames[]      | ListMcpResourcesTool                                 | |
| |                     | mcp__chrome-devtools__take_memory_snapshot           | |
| +---------------------+------------------------------------------------------+ |
|                                                                                |
| Pending MCP Servers                                                            |
| +---------------------+------------------------------------------------------+ |
| | pendingMcpServers[] | chrome-devtools                                      | |
| |                     | claude.ai Cloudflare Developer Platform              | |
| |                     | claude.ai Notion                                     | |
| +---------------------+------------------------------------------------------+ |
+--------------------------------------------------------------------------------+
```

Render the array sections as nested tables because the flattened fields carry repeated values. Keep the positive lists (`addedNames[]`, `addedLines[]`, `readdedNames[]`) visually distinct from the negative list (`removedNames[]`), and keep `pendingMcpServers[]` in its own nested table.
