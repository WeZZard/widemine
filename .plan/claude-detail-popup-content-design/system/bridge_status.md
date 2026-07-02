# Detail Popup Content Design - System / Bridge Status

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Content | `content` | Provides the user-visible bridge status message. | String status text announcing remote-control availability and the continuation link. | true |
| CWD | `cwd` | Records working-directory context for the transcript event. | Filesystem path string. | false |
| Entrypoint | `entrypoint` | Records the client entrypoint that emitted the event. | Short string such as `cli`. | false |
| Git Branch | `gitBranch` | Records repository branch context at event time. | Branch name string such as `main`. | false |
| Is Meta | `isMeta` | Records transcript metadata classification. | Boolean value. | false |
| Is Sidechain | `isSidechain` | Records transcript sidechain classification. | Boolean value. | false |
| Parent UUID | `parentUuid` | Links this event to its parent transcript item. | UUID string. | false |
| Session ID | `sessionId` | Identifies the transcript session for routing and traceability. | UUID string. | false |
| Slug | `slug` | Records the generated session slug when present. | Optional slug string. | false |
| Subtype | `subtype` | Routes the message to the second-level titlebar badge. | Constant string `bridge_status`. | false |
| Timestamp | `timestamp` | Places the event on the timeline. | ISO timestamp string. | false |
| Type | `type` | Routes the message to the first-level titlebar badge. | Constant string `system`. | false |
| URL | `url` | Provides the user-visible continuation target for the active bridge. | Claude session URL string. | true |
| User Type | `userType` | Records user-origin classification for the event. | String such as `external`. | false |
| UUID | `uuid` | Identifies the individual transcript item. | UUID string. | false |
| Version | `version` | Records the emitting client version. | Version string. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Content | `content` | Use the raw `content` value. | Render as wrapped status text with detected links clickable. |
| URL | `url` | Use the raw `url` value. | Render as a clickable URL with a copy action. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [System] [Bridge Status]                                      [pin] [x] |
+--------------------------------------------------------------------------+
|                         Content | Metadata | Raw                         |
+--------------------------------------------------------------------------+
| Content                                                                  |
| /remote-control is active ...                                            |
|                                                                          |
| URL                                                                      |
| https://claude.ai/code/session_...                              [copy]   |
+--------------------------------------------------------------------------+
```
