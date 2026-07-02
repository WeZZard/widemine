# System / Scheduled Task Fire

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `content` | Scheduled task fire text shown as the primary message body. | Required string; observed 11; max length 45; samples include `Claude resuming /loop wakeup (Jun 15 10:01pm)` and later `/loop wakeup` resume times. | true | true |
| `cwd` | Working directory context for the scheduled task fire. | Required string; observed 11; max length 38; samples include `/Users/wezzard/Projects/product-driver` and `/Users/wezzard/Projects/rubberdux`. | true | false |
| `entrypoint` | Client entry surface that emitted the scheduled task fire event. | Required string; observed 11; max length 3; constant sample `cli`. | true | false |
| `gitBranch` | Repository branch context for the scheduled task fire. | Required string; observed 11; max length 19; samples include `main` and `feat/whiteboard-gui`. | true | false |
| `isMeta` | Raw transcript metadata classification flag. | Required bool; observed 11; constant sample `false`. | false | false |
| `isSidechain` | Raw transcript sidechain routing flag. | Required bool; observed 11; constant sample `false`. | false | false |
| `parentUuid` | Parent transcript record identifier. | Required string; observed 11; max length 36. | false | false |
| `sessionId` | Transcript session identifier used for raw trace correlation. | Required string; observed 11; max length 36; samples include `23c26bf5-6a03-4cc2-b048-ac153243916a` and `37ebbf38-b99e-4e64-a45a-68ef5bc86790`. | false | false |
| `slug` | Scan or session slug metadata. | Required string; observed 11; max length 46; samples include `read-agentic-routines-md-continue-mossy-noodle` and `currently-rubberdux-has-implemented-gentle-sky`. | false | false |
| `subtype` | Raw subtype discriminator for routing. | Required string; observed 11; max length 19; constant `scheduled_task_fire`. | false | false |
| `timestamp` | Event time for sorting and display. | Required string; observed 11; max length 24; samples include `2026-06-15T14:01:00.248Z` and `2026-06-16T09:00:00.837Z`. | false | false |
| `type` | Raw type discriminator for routing. | Required string; observed 11; max length 6; constant `system`. | false | false |
| `userType` | Transcript user category metadata. | Required string; observed 11; max length 8; constant `external`. | false | false |
| `uuid` | Transcript record identifier. | Required string; observed 11; max length 36. | false | false |
| `version` | Producer version metadata. | Required string; observed 11; max length 7; constant sample `2.1.177`. | false | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Scheduled Task Fire | `{content}` |
| Working Directory | `{cwd}` |
| Entrypoint | `{entrypoint}` |
| Git Branch | `{gitBranch}` |

## Message Navigation Item Design

Use `System / Scheduled Task Fire` as the two-level category. Line 1 keeps the category and subtype on the left and the formatted event time on the right. Line 2 uses the summary contents from `content`, truncated only for navigation width.

```text
System / Scheduled Task Fire .......................................... {time}
{content}
```

## Message Card Design

Render the card with the system-slate tone and full first-level and second-level badges. The content form shows the scheduled task fire text first, then the visible workspace context. No array fields are present in the compiled shape, so no nested array table is required.

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [System] [Scheduled Task Fire]  {time}  agent/path        [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Scheduled Task                                                                 |
| +----------------------------------------------------------------------------+ |
| | {content}                                                                  | |
| +----------------------------------------------------------------------------+ |
|                                                                                |
| Workspace Context                                                              |
| +-------------------+------------------------------------------------------+   |
| | Working Directory | {cwd}                                                |   |
| | Entrypoint        | {entrypoint}                                         |   |
| | Git Branch        | {gitBranch}                                          |   |
| +-------------------+------------------------------------------------------+   |
|                                                                                |
| Trace Context                                                                  |
| +-------------------+------------------------------------------------------+   |
| | Timestamp         | {timestamp}                                          |   |
| | Session ID        | {sessionId}                                          |   |
| +-------------------+------------------------------------------------------+   |
+--------------------------------------------------------------------------------+
```
