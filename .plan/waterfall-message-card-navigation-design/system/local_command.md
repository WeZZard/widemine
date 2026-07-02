# System / Local Command

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `content` | Local command invocation or local command stdout text shown as the primary message body. | Required string; observed 78 across 3 shapes; max length 172; samples include `<command-name>/mcp</command-name> ...` and `<local-command-stdout>Resume cancelled</local-command-stdout>`. | true | true |
| `cwd` | Working directory context for the local command event. | Required string; observed 78; max length 106; samples include `/Users/wezzard`, repository paths, and plan directories. | true | false |
| `entrypoint` | Client entry surface that emitted the local command event. | Required string; observed 78; max length 3; constant sample `cli`. | true | false |
| `gitBranch` | Repository branch context for the local command event. | Required string; observed 78; max length 19; samples include `HEAD`, `main`, `dev`, `humanize-source`, and `feat/whiteboard-gui`. | true | false |
| `isMeta` | Raw transcript metadata classification flag. | Required bool; observed 78; constant sample `false`. | false | false |
| `isSidechain` | Raw transcript sidechain routing flag. | Required bool; observed 78; constant sample `false`. | false | false |
| `level` | Raw system log severity for the local command event. | Required string; observed 78; max length 4; constant sample `info`. | false | false |
| `parentUuid` | Parent transcript record identifier, nullable in one observed shape. | Required string or null; observed 78; 77 UUID strings and 1 null. | false | false |
| `sessionId` | Transcript session identifier. | Required string; observed 78; max length 36. | false | false |
| `slug` | Optional scan or session slug metadata. | Optional string; observed 51 of 78; max length 49. | false | false |
| `subtype` | Raw subtype discriminator for routing. | Required string; observed 78; max length 13; constant `local_command`. | false | false |
| `timestamp` | Event time for sorting and display. | Required string; observed 78; max length 24. | false | false |
| `type` | Raw type discriminator for routing. | Required string; observed 78; max length 6; constant `system`. | false | false |
| `userType` | Transcript user category metadata. | Required string; observed 78; max length 8; constant `external`. | false | false |
| `uuid` | Transcript record identifier. | Required string; observed 78; max length 36. | false | false |
| `version` | Producer version metadata. | Required string; observed 78; max length 7; samples include `2.1.162`, `2.1.181`, and `2.1.185`. | false | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Local Command | `{content}` |
| Working Directory | `{cwd}` |
| Entrypoint | `{entrypoint}` |
| Git Branch | `{gitBranch}` |

## Message Navigation Item Design

Use `System / Local Command` as the two-level category. Line 1 keeps the category and subtype on the left and the formatted event time on the right. Line 2 uses the summary contents from `content`, preserving command or stdout text and clipping only for navigation width.

```text
System / Local Command ................................................. {time}
{content}
```

## Message Card Design

Render the card with the system-slate tone and full first-level and second-level badges. The content form keeps the local command text first, then the visible command context. No array fields are present in the compiled shapes, so no nested array table is required.

```text
+--------------------------------------------------------------------------------+
| o  [System] [Local Command]  {time}  agent/path              [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Local Command                                                                  |
| +----------------------------------------------------------------------------+ |
| | {content}                                                                  | |
| +----------------------------------------------------------------------------+ |
|                                                                                |
| Command Context                                                                |
| +-------------------+------------------------------------------------------+   |
| | Working Directory | {cwd}                                                |   |
| | Entrypoint        | {entrypoint}                                         |   |
| | Git Branch        | {gitBranch}                                          |   |
| +-------------------+------------------------------------------------------+   |
+--------------------------------------------------------------------------------+
```
