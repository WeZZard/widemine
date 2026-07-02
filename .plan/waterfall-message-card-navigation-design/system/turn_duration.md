# System / Turn Duration

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `cwd` | Shows the working directory context for the completed turn. | string; count 949; max length 135; samples include `/Users/wezzard` and repository paths | true | false |
| `durationMs` | Primary elapsed-time result for the completed turn. | number; count 949; samples include `80269`, `587770`, and `1969491` | true | true |
| `entrypoint` | Shows the runtime entry surface for the completed turn. | string; count 949; max length 3; constant sample `cli` | true | false |
| `gitBranch` | Shows the branch context for the completed turn. | string; count 949; max length 32; samples include `HEAD`, `main`, `dev`, and worktree branch names | true | false |
| `isMeta` | Raw transcript metadata classification flag. | bool; count 949; constant sample `false` | false | false |
| `isSidechain` | Raw transcript sidechain routing flag. | bool; count 949; constant sample `false` | false | false |
| `messageCount` | Secondary transcript-position count for the completed turn. | number; count 949; samples include `28`, `304`, and `236` | true | false |
| `parentUuid` | Links this event to its parent transcript entry. | UUID string; count 949; max length 36 | false | false |
| `pendingBackgroundAgentCount` | Optional visible pending-background-agent count after the turn. | number; count 249; samples include `1`, `2`, `3`, `4`, `5`, `7`, and `12` | true | false |
| `pendingWorkflowCount` | Optional visible pending-workflow count after the turn. | number; count 24; sample `1` | true | false |
| `sessionId` | Links this event to its transcript session. | UUID string; count 949; max length 36 | false | false |
| `slug` | Optional raw session or scan slug metadata. | string; count 757; max length 53; samples include `cached-skipping-moth` and `joyful-juggling-crane` | false | false |
| `subtype` | Raw subtype discriminator used for routing. | string; count 949; max length 13; constant `turn_duration` | false | false |
| `timestamp` | Supplies the visible event time for navigation and card chrome. | ISO timestamp string; count 949; max length 24; sample `2026-06-09T05:15:57.763Z` | false | false |
| `type` | Raw type discriminator used for routing. | string; count 949; max length 6; constant `system` | false | false |
| `userType` | Raw transcript user category metadata. | string; count 949; max length 8; constant `external` | false | false |
| `uuid` | Identifies this transcript event. | UUID string; count 949; max length 36 | false | false |
| `version` | Records the emitting client version. | string; count 949; max length 7; samples include `2.1.169`, `2.1.181`, and `2.1.185` | false | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Working Directory | `{cwd}` |
| Duration Ms | `{durationMs}` |
| Entrypoint | `{entrypoint}` |
| Git Branch | `{gitBranch}` |
| Message Count | `{messageCount}` |
| Pending Background Agent Count | `{pendingBackgroundAgentCount}` |
| Pending Workflow Count | `{pendingWorkflowCount}` |

## Message Navigation Item Design

Use `System / Turn Duration` as the two-level category. The first line keeps the category and subtype on the left and the formatted event time on the right. The second line is the duration summary, followed by message count and any pending counters that are present.

```text
System / Turn Duration ................................................ {time}
{durationMs} ms; {messageCount} messages; bg agents {pendingBackgroundAgentCount}; workflows {pendingWorkflowCount}
```

## Message Card Design

Render the card with a compact title bar and a direct content form. No array fields are present in the compiled shapes, so no nested array table is required.

```text
+-- o System / Turn Duration ------- {time} -- main -- Raw -- Copy JSON --+
| Content Form                                                             |
|                                                                          |
| Field                             Value                                  |
| --------------------------------  -------------------------------------  |
| Duration Ms                       {durationMs}                           |
| Message Count                     {messageCount}                         |
| Pending Background Agent Count    {pendingBackgroundAgentCount}          |
| Pending Workflow Count            {pendingWorkflowCount}                 |
| Working Directory                 {cwd}                                  |
| Git Branch                        {gitBranch}                            |
| Entrypoint                        {entrypoint}                           |
+--------------------------------------------------------------------------+
```
