# System / Bridge Status

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `content` | Primary bridge status text shown to the user. | Required string; observed 5 across 2 shapes; max length 119; announces `/remote-control` availability and includes the continuation link. | true | true |
| `cwd` | Working directory context for the bridged session. | Required string; observed 5; max length 106; samples include project and plan-directory paths. | true | false |
| `entrypoint` | Client entry surface that emitted the bridge status. | Required string; observed 5; max length 3; constant sample `cli`. | true | false |
| `gitBranch` | Repository branch context for the bridged session. | Required string; observed 5; max length 4; constant sample `main`. | true | false |
| `isMeta` | Raw transcript metadata classification flag. | Required bool; observed 5; constant sample `false`. | false | false |
| `isSidechain` | Raw transcript sidechain routing flag. | Required bool; observed 5; constant sample `false`. | false | false |
| `parentUuid` | Parent transcript record identifier. | Required string; observed 5; max length 36. | false | false |
| `sessionId` | Transcript session identifier for the bridge target. | Required string; observed 5; max length 36. | true | false |
| `slug` | Optional raw session or scan slug metadata. | Optional string; observed 3 of 5; max length 44. | false | false |
| `subtype` | Raw subtype discriminator used for routing. | Required string; observed 5; max length 13; constant sample `bridge_status`. | false | false |
| `timestamp` | Event time for sorting and display. | Required string; observed 5; max length 24. | false | false |
| `type` | Raw type discriminator used for routing. | Required string; observed 5; max length 6; constant sample `system`. | false | false |
| `url` | Canonical continuation URL for the active bridge. | Required string; observed 5; max length 55; Claude session URL. | true | false |
| `userType` | Raw transcript user category metadata. | Required string; observed 5; max length 8; constant sample `external`. | false | false |
| `uuid` | Transcript record identifier for this bridge status event. | Required string; observed 5; max length 36. | false | false |
| `version` | Producer version metadata. | Required string; observed 5; max length 7; samples include `2.1.148`, `2.1.185`, and `2.1.150`. | false | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Bridge Status | `{content}` |
| Bridge URL | `{url}` |
| Session ID | `{sessionId}` |
| Working Directory | `{cwd}` |
| Git Branch | `{gitBranch}` |
| Entrypoint | `{entrypoint}` |

## Message Navigation Item Design

Use `System / Bridge Status` as the two-level category. Line 1 keeps the category and subtype on the left and the formatted event time on the right. Line 2 uses the summary contents from `content`, clipped only for navigation width.

```text
System / Bridge Status ............................................... {time}
{content}
```

## Message Card Design

Render the card with the system-slate tone and full first-level and second-level badges. The content form shows the status text and continuation URL first, followed by the direct bridge session context. No array fields are present in the compiled shapes, so no nested array table is required.

```text
+--------------------------------------------------------------------------------+
| o  [System] [Bridge Status]  {time}  agent/path              [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Bridge Connection                                                              |
| +-------------------+------------------------------------------------------+   |
| | Bridge Status     | {content}                                            |   |
| | Bridge URL        | {url}                                                |   |
| +-------------------+------------------------------------------------------+   |
|                                                                                |
| Session Context                                                                |
| +-------------------+------------------------------------------------------+   |
| | Session ID        | {sessionId}                                          |   |
| | Working Directory | {cwd}                                                |   |
| | Git Branch        | {gitBranch}                                          |   |
| | Entrypoint        | {entrypoint}                                         |   |
| +-------------------+------------------------------------------------------+   |
+--------------------------------------------------------------------------------+
```
