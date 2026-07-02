# Detail Popup Content Design - System / Compact Boundary

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Agent ID | `agentId` | Identifies the sidechain agent that emitted the boundary when present. | Optional string agent identifier; observed on sidechain shapes. | false |
| Compact Metadata | `compactMetadata` | Structural container for compaction details. | Object container; child paths hold token counts, trigger, preserved messages, and preserved segment data. | false |
| Duration Ms | `compactMetadata.durationMs` | Shows how long the compaction step took. | Number of milliseconds; observed from near-zero values through long-running compactions. | true |
| Post Tokens | `compactMetadata.postTokens` | Shows the token count after compaction. | Numeric token count after the compacted transcript was produced. | true |
| Pre Compact Discovered Tools | `compactMetadata.preCompactDiscoveredTools` | Holds the tool names known before compaction when recorded. | Optional array of strings; observed with up to 18 items. | true |
| Pre Compact Discovered Tools Item | `compactMetadata.preCompactDiscoveredTools[]` | Carries each tool name known before compaction. | String item such as `EnterPlanMode`, `ExitPlanMode`, or `EnterWorktree`. | true |
| Pre Tokens | `compactMetadata.preTokens` | Shows the token count before compaction. | Numeric token count before the compacted transcript was produced. | true |
| Precomputed | `compactMetadata.precomputed` | Shows whether the compacted result was precomputed when recorded. | Optional boolean; observed as `true` when present. | true |
| Preserved Messages | `compactMetadata.preservedMessages` | Structural container for preserved-message identifiers. | Object container; child paths hold anchor and UUID list fields. | false |
| All UUIDs | `compactMetadata.preservedMessages.allUuids` | Holds the full preserved-message UUID list when recorded. | Optional array of UUID strings; observed with up to 854 items. | true |
| All UUIDs Item | `compactMetadata.preservedMessages.allUuids[]` | Carries each UUID in the full preserved-message list. | String UUID item. | true |
| Anchor UUID | `compactMetadata.preservedMessages.anchorUuid` | Identifies the preserved-message anchor. | String UUID. | true |
| UUIDs | `compactMetadata.preservedMessages.uuids` | Holds the preserved-message UUID list. | Array of UUID strings; observed with up to 854 items. | true |
| UUIDs Item | `compactMetadata.preservedMessages.uuids[]` | Carries each UUID in the preserved-message list. | String UUID item. | true |
| Preserved Segment | `compactMetadata.preservedSegment` | Structural container for the compacted transcript segment boundaries. | Object container; child paths hold anchor, head, and tail UUIDs. | false |
| Anchor UUID | `compactMetadata.preservedSegment.anchorUuid` | Identifies the preserved segment anchor. | String UUID. | true |
| Head UUID | `compactMetadata.preservedSegment.headUuid` | Identifies the first message in the preserved segment. | String UUID. | true |
| Tail UUID | `compactMetadata.preservedSegment.tailUuid` | Identifies the last message in the preserved segment. | String UUID. | true |
| Trigger | `compactMetadata.trigger` | Shows what triggered the compaction boundary. | String trigger value; observed as `auto`. | true |
| Content | `content` | Shows the visible compacted-conversation marker. | String value; observed as `Conversation compacted`. | true |
| CWD | `cwd` | Records working directory context for metadata and trace views. | String filesystem path. | false |
| Entrypoint | `entrypoint` | Records the runtime surface that emitted the event. | String such as `cli` or `claude-vscode`. | false |
| Git Branch | `gitBranch` | Records repository branch context for metadata and trace views. | String branch or detached-head label. | false |
| Is Meta | `isMeta` | Records transcript metadata classification. | Boolean flag; observed as `false`. | false |
| Is Sidechain | `isSidechain` | Records transcript sidechain routing state. | Boolean flag. | false |
| Level | `level` | Records the system log level. | String value; observed as `info`. | false |
| Logical Parent UUID | `logicalParentUuid` | Links the boundary to its logical parent transcript item. | String UUID. | false |
| Parent UUID | `parentUuid` | Links the boundary to a parent transcript item. | Null in observed shapes. | false |
| Session ID | `sessionId` | Links the boundary to the containing transcript session. | String UUID. | false |
| Slug | `slug` | Records the generated conversation slug. | String slug. | false |
| Subtype | `subtype` | Routes the event to subtype-specific handling and titlebar badges. | Constant string `compact_boundary`. | false |
| Timestamp | `timestamp` | Records event time for timeline ordering. | ISO timestamp string. | false |
| Type | `type` | Routes the event to type-specific handling and titlebar badges. | Constant string `system`. | false |
| User Type | `userType` | Records user-origin classification for metadata and trace views. | String value; observed as `external`. | false |
| UUID | `uuid` | Identifies this transcript item. | String UUID. | false |
| Version | `version` | Records the emitting client version. | String version value. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Duration Ms | `compactMetadata.durationMs` | Direct value from `compactMetadata.durationMs`; show `Not provided` when absent. | Render as a numeric duration row with milliseconds as the displayed unit. |
| Post Tokens | `compactMetadata.postTokens` | Direct value from `compactMetadata.postTokens`; show `Not provided` when absent. | Render as a right-aligned integer token count. |
| Pre Compact Discovered Tools | `compactMetadata.preCompactDiscoveredTools` | Direct array from `compactMetadata.preCompactDiscoveredTools`; item rows come from `compactMetadata.preCompactDiscoveredTools[]`. | Render as a nested one-column `Pre Compact Discovered Tools` group; empty or missing array renders `Not provided`. |
| Pre Compact Discovered Tools Item | `compactMetadata.preCompactDiscoveredTools[]` | Each string item in `compactMetadata.preCompactDiscoveredTools`. | Render inside the `Pre Compact Discovered Tools` group under `Item`; never as an unrelated top-level row. |
| Pre Tokens | `compactMetadata.preTokens` | Direct value from `compactMetadata.preTokens`; show `Not provided` when absent. | Render as a right-aligned integer token count. |
| Precomputed | `compactMetadata.precomputed` | Direct value from `compactMetadata.precomputed`; show `Not provided` when absent. | Render as a boolean scalar. |
| All UUIDs | `compactMetadata.preservedMessages.allUuids` | Direct array from `compactMetadata.preservedMessages.allUuids`; item rows come from `compactMetadata.preservedMessages.allUuids[]`. | Render as a nested one-column `All UUIDs` group inside preserved messages; load every item directly and show the item count in the header. |
| All UUIDs Item | `compactMetadata.preservedMessages.allUuids[]` | Each string item in `compactMetadata.preservedMessages.allUuids`. | Render inside the `All UUIDs` group under `Item` as compact copyable UUID text. |
| Anchor UUID | `compactMetadata.preservedMessages.anchorUuid` | Direct value from `compactMetadata.preservedMessages.anchorUuid`; show `Not provided` when absent. | Render as a compact copyable identifier in the preserved messages group. |
| UUIDs | `compactMetadata.preservedMessages.uuids` | Direct array from `compactMetadata.preservedMessages.uuids`; item rows come from `compactMetadata.preservedMessages.uuids[]`. | Render as a nested one-column `UUIDs` group inside preserved messages; load every item directly and show the item count in the header. |
| UUIDs Item | `compactMetadata.preservedMessages.uuids[]` | Each string item in `compactMetadata.preservedMessages.uuids`. | Render inside the `UUIDs` group under `Item` as compact copyable UUID text. |
| Anchor UUID | `compactMetadata.preservedSegment.anchorUuid` | Direct value from `compactMetadata.preservedSegment.anchorUuid`; show `Not provided` when absent. | Render as a compact copyable identifier in the preserved segment group. |
| Head UUID | `compactMetadata.preservedSegment.headUuid` | Direct value from `compactMetadata.preservedSegment.headUuid`; show `Not provided` when absent. | Render as a compact copyable identifier in the preserved segment group. |
| Tail UUID | `compactMetadata.preservedSegment.tailUuid` | Direct value from `compactMetadata.preservedSegment.tailUuid`; show `Not provided` when absent. | Render as a compact copyable identifier in the preserved segment group. |
| Trigger | `compactMetadata.trigger` | Direct value from `compactMetadata.trigger`; show `Not provided` when absent. | Render as a short scalar value. |
| Content | `content` | Direct value from `content`; show `Not provided` when absent. | Render as a full-width text value. |

## Card Design

```text
+--------------------------------------------------------------------------------+
| [System] [Compact Boundary]                                         [pin] [x]  |
+--------------------------------------------------------------------------------+
|                            Content | Metadata | Raw                            |
+--------------------------------------------------------------------------------+
| Content                 <content>                                              |
| Trigger                 <compactMetadata.trigger>                              |
| Duration Ms             <compactMetadata.durationMs> ms                         |
| Pre Tokens              <compactMetadata.preTokens>                             |
| Post Tokens             <compactMetadata.postTokens>                            |
| Precomputed             <compactMetadata.precomputed>                           |
|                                                                                |
| Pre Compact Discovered Tools                                                   |
|   +------------------------------------------------------------------------+   |
|   | Item                                                                   |   |
|   | <compactMetadata.preCompactDiscoveredTools[]>                          |   |
|   | ...                                                                    |   |
|   +------------------------------------------------------------------------+   |
|                                                                                |
| Preserved Messages                                                             |
|   Anchor UUID        <compactMetadata.preservedMessages.anchorUuid>             |
|   All UUIDs                                                                    |
|   +------------------------------------------------------------------------+   |
|   | Item                                                                   |   |
|   | <compactMetadata.preservedMessages.allUuids[]>                         |   |
|   | ...                                                                    |   |
|   +------------------------------------------------------------------------+   |
|   UUIDs                                                                        |
|   +------------------------------------------------------------------------+   |
|   | Item                                                                   |   |
|   | <compactMetadata.preservedMessages.uuids[]>                            |   |
|   | ...                                                                    |   |
|   +------------------------------------------------------------------------+   |
|                                                                                |
| Preserved Segment                                                              |
|   Anchor UUID        <compactMetadata.preservedSegment.anchorUuid>              |
|   Head UUID          <compactMetadata.preservedSegment.headUuid>                |
|   Tail UUID          <compactMetadata.preservedSegment.tailUuid>                |
+--------------------------------------------------------------------------------+
```
