# System / Informational

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `content` | Informational system message text shown as the primary message body and navigation preview. | Required string; observed 4 across 2 shapes; max length 501; samples include `Auto mode lets Claude handle permission prompts automatically...` and `Remote Control disconnected: Transport closed (code 4090)`. | true | true |
| `cwd` | Working directory context for the informational system message. | Required string; observed 4; max length 33; samples include `/Users/wezzard/Projects/rubberdux` and `/Users/wezzard`. | true | false |
| `entrypoint` | Client entry surface that emitted the informational system message. | Required string; observed 4; max length 3; constant sample `cli`. | true | false |
| `gitBranch` | Repository branch context for the informational system message. | Required string; observed 4; max length 4; samples include `main` and `HEAD`. | true | false |
| `isMeta` | Raw transcript metadata classification flag. | Required bool; observed 4; constant sample `false`. | false | false |
| `isSidechain` | Raw transcript sidechain routing flag. | Required bool; observed 4; constant sample `false`. | false | false |
| `level` | Visible informational severity level for the system message. | Required string; observed 4; max length 7; samples include `warning`, `notice`, and `info`. | true | false |
| `parentUuid` | Parent transcript record identifier. | Required string; observed 4; max length 36. | false | false |
| `sessionId` | Transcript session identifier. | Required string; observed 4; max length 36. | false | false |
| `slug` | Optional scan or session slug metadata. | Optional string; observed 2 of 4; max length 44. | false | false |
| `subtype` | Raw subtype discriminator for routing. | Required string; observed 4; max length 13; constant `informational`. | false | false |
| `timestamp` | Event time for sorting and display in navigation and card chrome. | Required string; observed 4; max length 24; samples include `2026-05-26T11:56:35.991Z` and `2026-06-05T02:52:11.743Z`. | false | false |
| `type` | Raw type discriminator for routing. | Required string; observed 4; max length 6; constant `system`. | false | false |
| `userType` | Raw transcript user category metadata. | Required string; observed 4; max length 8; constant `external`. | false | false |
| `uuid` | Transcript record identifier. | Required string; observed 4; max length 36. | false | false |
| `version` | Producer version metadata. | Required string; observed 4; max length 7; samples include `2.1.148` and `2.1.162`. | false | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Information | `{content}` |
| Level | `{level}` |
| Working Directory | `{cwd}` |
| Entrypoint | `{entrypoint}` |
| Git Branch | `{gitBranch}` |

## Message Navigation Item Design

Use `System / Informational` as the two-level category. Line 1 keeps the category and subtype on the left and the formatted event time on the right. Line 2 uses the summary contents from `content`, truncated only for navigation width.

```text
System / Informational ................................................ {time}
{content}
```

## Message Card Design

Render the card with the system-slate tone and full first-level and second-level badges. The content form shows the informational message and level first, then the visible workspace context. No array fields are present in the compiled shapes, so no nested array table is required.

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [System] [Informational]  {time}  agent/path              [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Information                                                                    |
| +----------------------------------------------------------------------------+ |
| | {content}                                                                  | |
| +----------------------------------------------------------------------------+ |
|                                                                                |
| Message Details                                                                |
| +-------------------+------------------------------------------------------+   |
| | Level             | {level}                                              |   |
| +-------------------+------------------------------------------------------+   |
|                                                                                |
| Workspace Context                                                              |
| +-------------------+------------------------------------------------------+   |
| | Working Directory | {cwd}                                                |   |
| | Entrypoint        | {entrypoint}                                         |   |
| | Git Branch        | {gitBranch}                                          |   |
| +-------------------+------------------------------------------------------+   |
+--------------------------------------------------------------------------------+
```
