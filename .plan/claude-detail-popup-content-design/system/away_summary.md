# Detail Popup Content Design - System / Away Summary

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Content | `content` | Carries the away-mode recap, including goal state, result, blocker, or next action. | Types: string. Count: 90. Max length: 365. | true |
| CWD | `cwd` | Records working-directory context for traceability. | Types: string. Count: 90. Max length: 135. | false |
| Entrypoint | `entrypoint` | Records the runtime entrypoint that produced the event. | Types: string. Count: 90. Max length: 3. | false |
| Git Branch | `gitBranch` | Records repository branch context for metadata and trace views. | Types: string. Count: 90. Max length: 29. | false |
| Is Meta | `isMeta` | Transcript bookkeeping flag for meta-level events. | Types: bool. Count: 90. | false |
| Is Sidechain | `isSidechain` | Transcript routing flag for sidechain events. | Types: bool. Count: 90. | false |
| Parent UUID | `parentUuid` | Links this event to its parent transcript record. | Types: string. Count: 90. Max length: 36. | false |
| Session ID | `sessionId` | Links this event to its containing transcript session. | Types: string. Count: 90. Max length: 36. | false |
| Slug | `slug` | Records the generated conversation slug when present. | Types: string. Count: 52. Max length: 53. | false |
| Subtype | `subtype` | Routing identity already represented by the popup titlebar. | Types: string. Count: 90. Max length: 12. | false |
| Timestamp | `timestamp` | Records event time for timeline ordering and metadata display. | Types: string. Count: 90. Max length: 24. | false |
| Type | `type` | Routing identity already represented by the popup titlebar. | Types: string. Count: 90. Max length: 6. | false |
| User Type | `userType` | Records transcript participant classification metadata. | Types: string. Count: 90. Max length: 8. | false |
| UUID | `uuid` | Identifies this transcript record. | Types: string. Count: 90. Max length: 36. | false |
| Version | `version` | Records producer version metadata. | Types: string. Count: 90. Max length: 7. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Content | `content` | Raw `content` field from the message JSON. | Full-width multiline text row; preserve paragraph breaks and render complete long summaries in a bounded scroll area. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [System] [Away Summary]                                       [pin] [x] |
+--------------------------------------------------------------------------+
|                         Content | Metadata | Raw                         |
+--------------------------------------------------------------------------+
| Content                                                                  |
| <content>                                                                |
+--------------------------------------------------------------------------+
```
