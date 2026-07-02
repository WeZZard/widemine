# Detail Popup Content Design - System / Turn Duration

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Duration Ms | `durationMs` | Primary result for the turn timing summary. | Observed number of milliseconds recorded for the completed turn. | true |
| CWD | `cwd` | Records working directory context for metadata lookup. | Observed string filesystem path. | false |
| Entrypoint | `entrypoint` | Records runtime entry surface for metadata lookup. | Observed string; `cli`. | false |
| Git Branch | `gitBranch` | Records repository branch context for metadata lookup. | Observed string branch names such as `HEAD`, `main`, `dev`, or worktree branch names. | false |
| Is Meta | `isMeta` | Records transcript metadata classification. | Observed bool; `false`. | false |
| Is Sidechain | `isSidechain` | Records transcript sidechain routing state. | Observed bool; `false`. | false |
| Message Count | `messageCount` | Records transcript bookkeeping at the time of the duration event. | Observed number of transcript messages counted at this point. | false |
| Parent UUID | `parentUuid` | Links this duration event to its parent transcript entry. | Observed string UUID. | false |
| Pending Background Agent Count | `pendingBackgroundAgentCount` | Records internal background agent workflow state. | Optional observed number; present on one shape family. | false |
| Pending Workflow Count | `pendingWorkflowCount` | Records internal pending workflow state. | Optional observed number; present on two shape families. | false |
| Session ID | `sessionId` | Links the event to a transcript session. | Observed string UUID. | false |
| Slug | `slug` | Records scan or session slug metadata. | Optional observed string slug. | false |
| Subtype | `subtype` | Supports routing and titlebar identity; not repeated in Content. | Observed string; `turn_duration`. | false |
| Timestamp | `timestamp` | Records event time for ordering and metadata lookup. | Observed ISO timestamp string. | false |
| Type | `type` | Supports routing and titlebar identity; not repeated in Content. | Observed string; `system`. | false |
| User Type | `userType` | Records transcript user category metadata. | Observed string; `external`. | false |
| UUID | `uuid` | Identifies this transcript event. | Observed string UUID. | false |
| Version | `version` | Records emitting client version metadata. | Observed string version values. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Duration Ms | `durationMs` | Direct value from `durationMs`. | Render as a compact duration value with milliseconds available. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [System] [Turn Duration]                                      [pin] [x] |
+--------------------------------------------------------------------------+
|                         Content | Metadata | Raw                         |
+--------------------------------------------------------------------------+
| Duration Ms                         <value from durationMs>              |
+--------------------------------------------------------------------------+
```
