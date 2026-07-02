# Detail Popup Content Design - File History Snapshot / Raw Event

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Is Snapshot Update | `isSnapshotUpdate` | Indicates whether the snapshot record is an update rather than an initial snapshot. | Boolean; observed values are `false` and `true`. | true |
| Message ID | `messageId` | Identifies the wrapper event for trace correlation. | UUID string. | false |
| Snapshot Message ID | `snapshot.messageId` | Identifies the snapshot payload for trace correlation. | UUID string. | false |
| Timestamp | `snapshot.timestamp` | Shows when the file-history snapshot was captured. | ISO 8601 timestamp string. | true |
| File Path | `snapshot.trackedFileBackups.<filePath>` | Identifies each tracked backup entry by dynamic file path map key. | Path-keyed object entry; repeated once per tracked file. | true |
| Backup File Name | `snapshot.trackedFileBackups.<filePath>.backupFileName` | Names the stored backup artifact for the tracked file. | String backup token, or `null` when no stored backup name is present. | true |
| Backup Time | `snapshot.trackedFileBackups.<filePath>.backupTime` | Shows when the tracked file backup was captured. | ISO 8601 timestamp string. | true |
| Version | `snapshot.trackedFileBackups.<filePath>.version` | Shows the tracked file backup version number. | Number. | true |
| Type | `type` | Routes the raw record to the titlebar category. | Constant string value `file-history-snapshot`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Is Snapshot Update | `isSnapshotUpdate` | Read directly from `isSnapshotUpdate`. | Render as a compact boolean value. |
| Timestamp | `snapshot.timestamp` | Read directly from `snapshot.timestamp`. | Render as a single-line timestamp value. |
| File Path | `snapshot.trackedFileBackups.<filePath>` | For each key under `snapshot.trackedFileBackups`, use the key text as the file path. | Render in the Tracked File Backups nested table as a copyable path with middle truncation when needed. |
| Backup File Name | `snapshot.trackedFileBackups.<filePath>.backupFileName` | For each tracked file backup entry, read `backupFileName`. | Render in the Tracked File Backups nested table as a compact copyable value; show `null` plainly when present. |
| Backup Time | `snapshot.trackedFileBackups.<filePath>.backupTime` | For each tracked file backup entry, read `backupTime`. | Render in the Tracked File Backups nested table as a single-line timestamp value. |
| Version | `snapshot.trackedFileBackups.<filePath>.version` | For each tracked file backup entry, read `version`. | Render in the Tracked File Backups nested table as a compact numeric value. |

## Card Design

```text
+--------------------------------------------------------------------------------+
| [File History Snapshot] [Raw Event]                                    [pin] [x] |
+--------------------------------------------------------------------------------+
|                            Content | Metadata | Raw                             |
+--------------------------------------------------------------------------------+
| Is Snapshot Update  <isSnapshotUpdate>                                          |
| Timestamp           <snapshot.timestamp>                                        |
|                                                                                |
| Tracked File Backups                                                            |
|   | File Path  | Backup File Name  | Backup Time  | Version |                  |
|   | <filePath> | <backupFileName>  | <backupTime> | <version> |                |
|   | ...        | ...               | ...          | ...     |                  |
+--------------------------------------------------------------------------------+
```
