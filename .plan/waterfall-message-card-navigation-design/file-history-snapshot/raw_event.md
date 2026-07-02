# File History Snapshot

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| isSnapshotUpdate | Shows whether this file history event updates an existing snapshot. | boolean; samples `true`, `false` | true | false |
| messageId | Event message identifier used to correlate this raw snapshot event. | UUID string | true | false |
| snapshot | Snapshot payload container. | object with `messageId`, `timestamp`, and `trackedFileBackups` | false | false |
| snapshot.messageId | Message identifier stored inside the snapshot payload. | UUID string | true | false |
| snapshot.timestamp | Snapshot payload timestamp. | ISO 8601 string | true | false |
| snapshot.trackedFileBackups | Path-keyed map of tracked file backup entries. | object map keyed by file path; each entry contains `backupFileName`, `backupTime`, and `version` | true | true |
| snapshot.trackedFileBackups.{path} | Backup entry for one tracked file path. | object keyed by the tracked file path | false | false |
| snapshot.trackedFileBackups.{path}.backupFileName | Backup file name for the tracked path. | string or `null`; sample `cc24c1bbe7782975@v2` | true | false |
| snapshot.trackedFileBackups.{path}.backupTime | Backup timestamp for the tracked path. | ISO 8601 string | true | false |
| snapshot.trackedFileBackups.{path}.version | Backup version for the tracked path. | number | true | false |
| type | Raw event discriminator. | constant `file-history-snapshot` | false | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Snapshot Update | `{isSnapshotUpdate}` |
| Message ID | `{messageId}` |
| Snapshot Message ID | `{snapshot.messageId}` |
| Snapshot Time | `{snapshot.timestamp}` |
| Tracked File Backups | `{snapshot.trackedFileBackups}` |
| Backup File Name | `{snapshot.trackedFileBackups.{path}.backupFileName}` |
| Backup Time | `{snapshot.trackedFileBackups.{path}.backupTime}` |
| Version | `{snapshot.trackedFileBackups.{path}.version}` |

## Message Navigation Item Design

Use `File History Snapshot` as the first-level category. This kind has no second-level category.

```text
File History Snapshot ........................................ {time}
{trackedBackupCount} backups, update {isSnapshotUpdate}, latest {latestBackupTime}
```

When `trackedFileBackups` is empty, line 2 falls back to `update {isSnapshotUpdate}, snapshot {snapshot.messageId}`.

## Message Card Design

Render the card with a compact title bar and a content form. Treat `snapshot.trackedFileBackups` as a path-keyed map and render visible entries in a nested table.

```text
+-- o File History Snapshot -------- {time} -- main -- Raw -- Copy JSON --+
| Snapshot Update    {isSnapshotUpdate}                                    |
| Message ID         {messageId}                                            |
| Snapshot Message   {snapshot.messageId}                                   |
| Snapshot Time      {snapshot.timestamp}                                   |
|                                                                          |
| Tracked File Backups                                                      |
| +-- Path ---------------- Backup File -------- Backup Time ------ Ver --+ |
| | {path}                {backupFileName}   {backupTime}       {version} | |
| | {path}                {backupFileName}   {backupTime}       {version} | |
| +-----------------------------------------------------------------------+ |
+--------------------------------------------------------------------------+
```
