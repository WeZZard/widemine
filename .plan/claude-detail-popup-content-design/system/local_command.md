# Detail Popup Content Design - System / Local Command

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Content | `content` | Carries the local command invocation or the local command stdout that the user sees in the transcript. | String with command markup such as `command-name`, `command-message`, `command-args`, or `local-command-stdout`; observed in all 74 messages with max length 172. | true |
| CWD | `cwd` | Records working-directory context for trace and metadata review. | String path; observed in all 74 messages with max length 106. | false |
| Entrypoint | `entrypoint` | Records producer entrypoint context for trace and metadata review. | String value; observed value `cli`. | false |
| Git Branch | `gitBranch` | Records repository branch context for trace and metadata review. | String value such as `HEAD`, `main`, `dev`, or `feat/whiteboard-gui`; observed in all 74 messages with max length 19. | false |
| Is Meta | `isMeta` | Records metadata classification for trace and metadata review. | Boolean value; observed value `false`. | false |
| Is Sidechain | `isSidechain` | Records sidechain routing context for trace and metadata review. | Boolean value; observed value `false`. | false |
| Level | `level` | Records log severity for trace and metadata review. | String value; observed value `info`. | false |
| Parent UUID | `parentUuid` | Links the record to a parent transcript entry for navigation and trace review. | String UUID when present; null in one observed shape. | false |
| Session ID | `sessionId` | Links the record to its transcript session for metadata review. | String UUID. | false |
| Slug | `slug` | Records optional scan/session label context for trace and metadata review. | Optional string slug; observed in 47 of 74 messages with max length 49. | false |
| Subtype | `subtype` | Supports message routing and titlebar identity. | String value `local_command`. | false |
| Timestamp | `timestamp` | Records chronological trace context. | ISO timestamp string. | false |
| Type | `type` | Supports message routing and titlebar identity. | String value `system`. | false |
| User Type | `userType` | Records user/source routing context. | String value `external`. | false |
| UUID | `uuid` | Identifies the transcript record for trace and metadata review. | String UUID. | false |
| Version | `version` | Records producer version for trace and metadata review. | String version such as `2.1.170`, `2.1.181`, or `2.1.185`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Content | `content` | Use the recorded `content` value when present; show `Not provided` when absent. | Render as a complete preserved text block. Keep command tags visible, preserve line breaks, and place long content in a bounded scroll area without expand/collapse controls. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [System] / [Local Command]                                     [pin] [x] |
+--------------------------------------------------------------------------+
|                         Content | Metadata | Raw                         |
+--------------------------------------------------------------------------+
| Content                                                                  |
| ------------------------------------------------------------------------ |
| <content with command tags visible, wrapped, and scrollable when long>    |
+--------------------------------------------------------------------------+
```
