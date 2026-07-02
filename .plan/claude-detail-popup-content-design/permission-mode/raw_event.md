# Detail Popup Content Design - Permission Mode / Raw Event

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Permission Mode | `permissionMode` | Captures the effective permission mode recorded by the event. | String scalar; observed values include `bypassPermissions`, `auto`, `plan`, and `default`. | true |
| Session ID | `sessionId` | Correlates the event back to its source session. | UUID string. | false |
| Type | `type` | Provides top-level JSONL routing for the event family. | Constant string `permission-mode`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Permission Mode | `permissionMode` | Direct value from `permissionMode`. | Single-line scalar preserving exact casing. |

## Card Design

```text
+--------------------------------------------------------------------+
| [Permission Mode] [Raw Event]                            [pin] [x] |
+--------------------------------------------------------------------+
|                      Content | Metadata | Raw                      |
+--------------------------------------------------------------------+
| Permission Mode                                   <permissionMode> |
+--------------------------------------------------------------------+
```
