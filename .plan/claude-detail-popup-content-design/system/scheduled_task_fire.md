# Detail Popup Content Design - System / Scheduled Task Fire

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Content | `content` | Primary scheduled-task fire message to show in the Content tab. | String; required in all 11 observed messages; max length 45; wakeup/resume text such as `Claude resuming /loop wakeup (Jun 15 10:01pm)`. | true |
| CWD | `cwd` | Working-directory context for the transcript event; metadata only. | String; required in all 11 observed messages; project filesystem path. | false |
| Entrypoint | `entrypoint` | Launch source context for the transcript event; metadata only. | String; required in all 11 observed messages; observed value `cli`. | false |
| Git Branch | `gitBranch` | Repository branch context for the transcript event; metadata only. | String; required in all 11 observed messages; examples include `main` and `feat/whiteboard-gui`. | false |
| Is Meta | `isMeta` | Transcript classification flag; metadata only. | Boolean; required in all 11 observed messages; observed value `false`. | false |
| Is Sidechain | `isSidechain` | Conversation sidechain flag; metadata only. | Boolean; required in all 11 observed messages; observed value `false`. | false |
| Parent UUID | `parentUuid` | Parent message linkage; trace metadata only. | String UUID; required in all 11 observed messages. | false |
| Session ID | `sessionId` | Session linkage; trace metadata only. | String UUID; required in all 11 observed messages; two distinct observed sessions. | false |
| Slug | `slug` | Session slug for scan/navigation context; metadata only. | String; required in all 11 observed messages; max length 46. | false |
| Subtype | `subtype` | Routing discriminator already represented by the titlebar badge. | String; required in all 11 observed messages; observed value `scheduled_task_fire`. | false |
| Timestamp | `timestamp` | Event time for ordering and metadata panels; metadata only. | ISO timestamp string; required in all 11 observed messages. | false |
| Type | `type` | Routing discriminator already represented by the titlebar badge. | String; required in all 11 observed messages; observed value `system`. | false |
| User Type | `userType` | User/source classification for transcript context; metadata only. | String; required in all 11 observed messages; observed value `external`. | false |
| UUID | `uuid` | Message identifier; trace metadata only. | String UUID; required in all 11 observed messages. | false |
| Version | `version` | Producing client version context; metadata only. | String; required in all 11 observed messages; observed value `2.1.177`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Content | `content` | Use the exact `content` value from the message JSON. | Render as a full-width text field; preserve the value exactly and wrap naturally. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [System] [Scheduled Task Fire]                                  [pin] [x] |
+--------------------------------------------------------------------------+
|                         Content | Metadata | Raw                         |
+--------------------------------------------------------------------------+
| Content                                                                  |
| <content>                                                                |
+--------------------------------------------------------------------------+
```
