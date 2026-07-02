# System / Away Summary

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `content` | Generated away-mode recap and next-action text shown to the user. | Required string; observed 97 across 2 shapes; max length 365. | true | true |
| `cwd` | Working directory context for the away summary. | Required string; observed 97; max length 135. | true | false |
| `entrypoint` | Client entrypoint that produced the event. | Required string; observed 97; max length 3; constant sample `cli`. | false | false |
| `gitBranch` | Repository branch context for the away summary. | Required string; observed 97; max length 29; samples include `HEAD`, `main`, and worktree branch names. | true | false |
| `isMeta` | Raw transcript metadata classification flag. | Required bool; observed 97; constant sample `false`. | false | false |
| `isSidechain` | Raw transcript sidechain routing flag. | Required bool; observed 97; constant sample `false`. | false | false |
| `parentUuid` | Parent transcript record identifier. | Required string; observed 97; max length 36. | false | false |
| `sessionId` | Transcript session identifier. | Required string; observed 97; max length 36. | false | false |
| `slug` | Optional scan or session slug metadata. | Optional string; observed 53 of 97; max length 53. | false | false |
| `subtype` | Raw subtype discriminator for routing. | Required string; observed 97; max length 12; constant sample `away_summary`. | false | false |
| `timestamp` | Event time for sorting and display. | Required string; observed 97; max length 24. | false | false |
| `type` | Raw type discriminator for routing. | Required string; observed 97; max length 6; constant sample `system`. | false | false |
| `userType` | Transcript user category metadata. | Required string; observed 97; max length 8; constant sample `external`. | false | false |
| `uuid` | Transcript record identifier. | Required string; observed 97; max length 36. | false | false |
| `version` | Producer version metadata. | Required string; observed 97; max length 7. | false | false |

## Derived Car Form Content

| Field | Source Field | Contents |
| --- | --- | --- |
| Away Summary | `content` | `{content}` |
| Working Directory | `cwd` | `{cwd}` |
| Git Branch | `gitBranch` | `{gitBranch}` |

## Message Navigation Item Design

```text
System / Away Summary ................................................ {time}
{content}
```

Line 1 is the category/subtype label, flexible spacer, and formatted event time. Line 2 is the summary contents from `content`, truncated only for navigation width. Render `System` and `Away Summary` as full badges with the system-slate tone.

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [System] [Away Summary]  {time}  agent/path                [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Away Summary                                                                   |
| +----------------------------------------------------------------------------+ |
| | {content}                                                                  | |
| +----------------------------------------------------------------------------+ |
|                                                                                |
| Workspace Context                                                              |
| +-------------------+------------------------------------------------------+   |
| | Working Directory | {cwd}                                                |   |
| | Git Branch        | {gitBranch}                                          |   |
| +-------------------+------------------------------------------------------+   |
+--------------------------------------------------------------------------------+
```

The card body is one content form. Show the generated `content` first because it is the only summary field, then show the key workspace context fields. No array fields are present in the compiled shapes, so no nested array table is required.
