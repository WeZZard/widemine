# Detail Popup Content Design - System / Informational

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Content | `content` | Main informational text emitted by the system message. | String; observed values include permission auto-mode notices and remote-control disconnect notices. | true |
| CWD | `cwd` | Working-directory context for traceability. | String path. | false |
| Entrypoint | `entrypoint` | Runtime entrypoint metadata. | String such as `cli`. | false |
| Git Branch | `gitBranch` | Repository branch metadata for traceability. | String branch or detached-head value. | false |
| Is Meta | `isMeta` | Transcript bookkeeping flag. | Boolean. | false |
| Is Sidechain | `isSidechain` | Transcript routing flag. | Boolean. | false |
| Level | `level` | Severity level supporting the informational content. | String; observed values include `warning`, `notice`, and `info`. | true |
| Parent UUID | `parentUuid` | Parent record linkage metadata. | UUID string. | false |
| Session ID | `sessionId` | Session linkage metadata. | UUID string. | false |
| Slug | `slug` | Optional transcript slug metadata. | String slug when present. | false |
| Subtype | `subtype` | Routing identity already represented by the popup titlebar. | String `informational`. | false |
| Timestamp | `timestamp` | Event ordering metadata already handled outside Content. | ISO timestamp string. | false |
| Type | `type` | Routing identity already represented by the popup titlebar. | String `system`. | false |
| User Type | `userType` | Transcript participant metadata. | String such as `external`. | false |
| UUID | `uuid` | Record identity metadata. | UUID string. | false |
| Version | `version` | Runtime version metadata. | Version string. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Content | `content` | Raw `content` field from the message JSON. | Multiline text row; preserve line breaks and render complete long values in a bounded scroll area. |
| Level | `level` | Raw `level` field from the message JSON. | Compact scalar row using the raw level text. |

## Card Design

```text
+------------------------------------------------------------------------+
| [System] [Informational]                                      [pin] [x] |
+------------------------------------------------------------------------+
|                         Content | Metadata | Raw                       |
+------------------------------------------------------------------------+
| Content   <content>                                                    |
| Level     <level>                                                      |
+------------------------------------------------------------------------+
```
