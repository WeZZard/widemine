# System / Compact Boundary

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `agentId` | Identifies the subagent that emitted the compact boundary when present. | Optional string; observed 10 of 19; max length 17. | false | false |
| `compactMetadata` | Parent object for compaction details. | Object; observed 19 of 19. | false | false |
| `compactMetadata.durationMs` | Duration of the compact operation. | Number; observed 19 of 19; samples include `0`, `1`, and `150885`. | true | false |
| `compactMetadata.postTokens` | Token count after compaction. | Number; observed 19 of 19; samples include `22635`, `80897`, and `131845`. | true | false |
| `compactMetadata.preCompactDiscoveredTools` | Tool names discovered before compaction. | Array; observed 12 of 19; max 18 items. | true | false |
| `compactMetadata.preCompactDiscoveredTools[]` | One discovered tool name inside `compactMetadata.preCompactDiscoveredTools`. | Repeated string rows; observed 60 rows; max length 43; samples include `EnterPlanMode`, `EnterWorktree`, and `ExitPlanMode`. | false | false |
| `compactMetadata.preTokens` | Token count before compaction. | Number; observed 19 of 19; samples include `167078`, `194585`, and `1004818`. | true | false |
| `compactMetadata.precomputed` | Indicates whether the compact result was precomputed. | Bool; observed 14 of 19; constant sample `true`. | true | false |
| `compactMetadata.preservedMessages` | Parent object for preserved-message identifiers. | Object; observed 19 of 19. | false | false |
| `compactMetadata.preservedMessages.allUuids` | Full preserved-message UUID list when emitted. | Array; observed 18 of 19; max 854 items. | true | false |
| `compactMetadata.preservedMessages.allUuids[]` | One UUID inside `compactMetadata.preservedMessages.allUuids`. | Repeated string rows; observed 180 rows; max length 36. | false | false |
| `compactMetadata.preservedMessages.anchorUuid` | Anchor message UUID for the preserved messages. | String; observed 19 of 19; max length 36. | true | false |
| `compactMetadata.preservedMessages.uuids` | Preserved-message UUID list. | Array; observed 19 of 19; max 854 items. | true | false |
| `compactMetadata.preservedMessages.uuids[]` | One UUID inside `compactMetadata.preservedMessages.uuids`. | Repeated string rows; observed 184 rows; max length 36. | false | false |
| `compactMetadata.preservedSegment` | Parent object for preserved segment boundaries. | Object; observed 19 of 19. | false | false |
| `compactMetadata.preservedSegment.anchorUuid` | Anchor UUID for the preserved segment. | String; observed 19 of 19; max length 36. | true | false |
| `compactMetadata.preservedSegment.headUuid` | First preserved segment UUID. | String; observed 19 of 19; max length 36. | true | false |
| `compactMetadata.preservedSegment.tailUuid` | Last preserved segment UUID. | String; observed 19 of 19; max length 36. | true | false |
| `compactMetadata.trigger` | Trigger that caused compaction. | String; observed 19 of 19; max length 4; constant sample `auto`. | true | false |
| `content` | User-visible compact boundary message. | String; observed 19 of 19; max length 22; constant sample `Conversation compacted`. | true | true |
| `cwd` | Working directory context for the compact boundary. | String; observed 19 of 19; max length 71; samples include repository paths. | true | false |
| `entrypoint` | Client entrypoint that produced the event. | String; observed 19 of 19; max length 13; samples include `cli` and `claude-vscode`. | false | false |
| `gitBranch` | Repository branch context for the compact boundary. | String; observed 19 of 19; max length 19; samples include `HEAD`, `main`, and `feat/whiteboard-gui`. | true | false |
| `isMeta` | Raw transcript metadata classification flag. | Bool; observed 19 of 19; constant sample `false`. | false | false |
| `isSidechain` | Sidechain routing marker for compact boundaries emitted in subagent context. | Bool; observed 19 of 19; samples include `false` and `true`. | true | false |
| `level` | Raw event severity level. | String; observed 19 of 19; max length 4; constant sample `info`. | false | false |
| `logicalParentUuid` | Logical parent transcript record identifier. | String; observed 19 of 19; max length 36. | false | false |
| `parentUuid` | Parent transcript record identifier. | Null; observed 19 of 19. | false | false |
| `sessionId` | Transcript session identifier. | String; observed 19 of 19; max length 36. | false | false |
| `slug` | Raw scan or session slug metadata. | String; observed 19 of 19; max length 49. | false | false |
| `subtype` | Raw subtype discriminator for routing. | String; observed 19 of 19; max length 16; constant sample `compact_boundary`. | false | false |
| `timestamp` | Event time for sorting and display. | String; observed 19 of 19; max length 24. | false | false |
| `type` | Raw type discriminator for routing. | String; observed 19 of 19; max length 6; constant sample `system`. | false | false |
| `userType` | Transcript user category metadata. | String; observed 19 of 19; max length 8; constant sample `external`. | false | false |
| `uuid` | Transcript record identifier. | String; observed 19 of 19; max length 36. | false | false |
| `version` | Producer version metadata. | String; observed 19 of 19; max length 7; samples include `2.1.148`, `2.1.170`, and `2.1.183`. | false | false |

## Derived Car Form Content

| Field | Source Field | Contents |
| --- | --- | --- |
| Duration Ms | `compactMetadata.durationMs` | `{compactMetadata.durationMs}` |
| Post Tokens | `compactMetadata.postTokens` | `{compactMetadata.postTokens}` |
| Pre Compact Discovered Tools | `compactMetadata.preCompactDiscoveredTools` | `{compactMetadata.preCompactDiscoveredTools}` |
| Pre Tokens | `compactMetadata.preTokens` | `{compactMetadata.preTokens}` |
| Precomputed | `compactMetadata.precomputed` | `{compactMetadata.precomputed}` |
| Preserved Messages All UUIDs | `compactMetadata.preservedMessages.allUuids` | `{compactMetadata.preservedMessages.allUuids}` |
| Preserved Messages Anchor UUID | `compactMetadata.preservedMessages.anchorUuid` | `{compactMetadata.preservedMessages.anchorUuid}` |
| Preserved Messages UUIDs | `compactMetadata.preservedMessages.uuids` | `{compactMetadata.preservedMessages.uuids}` |
| Preserved Segment Anchor UUID | `compactMetadata.preservedSegment.anchorUuid` | `{compactMetadata.preservedSegment.anchorUuid}` |
| Preserved Segment Head UUID | `compactMetadata.preservedSegment.headUuid` | `{compactMetadata.preservedSegment.headUuid}` |
| Preserved Segment Tail UUID | `compactMetadata.preservedSegment.tailUuid` | `{compactMetadata.preservedSegment.tailUuid}` |
| Trigger | `compactMetadata.trigger` | `{compactMetadata.trigger}` |
| Content | `content` | `{content}` |
| Working Directory | `cwd` | `{cwd}` |
| Git Branch | `gitBranch` | `{gitBranch}` |
| Is Sidechain | `isSidechain` | `{isSidechain}` |

## Message Navigation Item Design

```text
System / Compact Boundary ............................................ {time}
{content}; trigger {compactMetadata.trigger}; tokens {compactMetadata.preTokens} -> {compactMetadata.postTokens}; sidechain {isSidechain}
```

Line 1 is the category/subtype label, flexible spacer, and formatted event time. Line 2 starts with the summary contents from `content`, then appends the compact trigger, before/after token counts, and sidechain marker. Render `System` and `Compact Boundary` as full badges with the system-slate tone.

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [System] [Compact Boundary]  {time}  agent/path            [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Compact Boundary                                                               |
| +----------------------+-----------------------------------------------------+ |
| | Content              | {content}                                           | |
| | Trigger              | {compactMetadata.trigger}                           | |
| | Pre Tokens           | {compactMetadata.preTokens}                         | |
| | Post Tokens          | {compactMetadata.postTokens}                        | |
| | Duration Ms          | {compactMetadata.durationMs}                        | |
| | Precomputed          | {compactMetadata.precomputed}                       | |
| | Is Sidechain         | {isSidechain}                                       | |
| +----------------------+-----------------------------------------------------+ |
|                                                                                |
| Preserved Segment                                                              |
| +----------------------+-----------------------------------------------------+ |
| | Head UUID            | {compactMetadata.preservedSegment.headUuid}         | |
| | Anchor UUID          | {compactMetadata.preservedSegment.anchorUuid}       | |
| | Tail UUID            | {compactMetadata.preservedSegment.tailUuid}         | |
| +----------------------+-----------------------------------------------------+ |
|                                                                                |
| Preserved Messages                                                             |
| +----------------------+-----------------------------------------------------+ |
| | Anchor UUID          | {compactMetadata.preservedMessages.anchorUuid}      | |
| | UUIDs                | nested table: compactMetadata.preservedMessages.uuids[]     | |
| | All UUIDs            | nested table: compactMetadata.preservedMessages.allUuids[]  | |
| +----------------------+-----------------------------------------------------+ |
|                                                                                |
| compactMetadata.preservedMessages.uuids[]                                      |
| +----+--------------------------------------+--------------------------------+ |
| | #  | UUID                                 | Source                         | |
| +----+--------------------------------------+--------------------------------+ |
| | 1  | {compactMetadata.preservedMessages.uuids[0]}     | uuids[0]          | |
| | 2  | {compactMetadata.preservedMessages.uuids[1]}     | uuids[1]          | |
| | .. | ...                                  | ...                            | |
| +----+--------------------------------------+--------------------------------+ |
|                                                                                |
| compactMetadata.preservedMessages.allUuids[]                                   |
| +----+--------------------------------------+--------------------------------+ |
| | #  | UUID                                 | Source                         | |
| +----+--------------------------------------+--------------------------------+ |
| | 1  | {compactMetadata.preservedMessages.allUuids[0]}  | allUuids[0]       | |
| | 2  | {compactMetadata.preservedMessages.allUuids[1]}  | allUuids[1]       | |
| | .. | ...                                  | ...                            | |
| +----+--------------------------------------+--------------------------------+ |
|                                                                                |
| Pre Compact Discovered Tools                                                   |
| +----+--------------------------------------+--------------------------------+ |
| | #  | Tool                                 | Source                         | |
| +----+--------------------------------------+--------------------------------+ |
| | 1  | {compactMetadata.preCompactDiscoveredTools[0]}   | tools[0]          | |
| | 2  | {compactMetadata.preCompactDiscoveredTools[1]}   | tools[1]          | |
| | .. | ...                                  | ...                            | |
| +----+--------------------------------------+--------------------------------+ |
|                                                                                |
| Workspace Context                                                              |
| +----------------------+-----------------------------------------------------+ |
| | Working Directory    | {cwd}                                               | |
| | Git Branch           | {gitBranch}                                         | |
| +----------------------+-----------------------------------------------------+ |
+--------------------------------------------------------------------------------+
```

Use compact message typography for scalar values and smaller balanced monospace for UUIDs, paths, and array table cells. Raw opens formatted raw JSON for this timeline item; Copy JSON copies the raw payload.
