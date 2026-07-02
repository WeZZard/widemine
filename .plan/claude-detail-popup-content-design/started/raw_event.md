# Detail Popup Content Design - Started / Raw Event

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Agent ID | `agentId` | Identifies the workflow agent associated with the start marker. | String identifier; observed length is 17 characters. | true |
| Key | `key` | Provides the event key paired with the workflow start marker. | String key; observed values commonly use a `v2:` prefix. | true |
| Type | `type` | Routes the record to the titlebar category. | Constant string value `started`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Agent ID | `agentId` | Read directly from `agentId`. | Single-line copyable identifier. |
| Key | `key` | Read directly from `key`. | Single-line copyable value with middle truncation when needed. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [Started] [Raw Event]                                          [pin] [x] |
+--------------------------------------------------------------------------+
|                         Content | Metadata | Raw                         |
+--------------------------------------------------------------------------+
| Agent ID     <agentId>                                                   |
| Key          <key>                                                       |
+--------------------------------------------------------------------------+
```
