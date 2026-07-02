# Detail Popup Content Design - Bridge Session / Raw Event

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Bridge Session ID | `bridgeSessionId` | Identifies the bridge session represented by the raw event. | String identifier, present on every observed message. | true |
| Last Sequence Num | `lastSequenceNum` | Shows the latest observed event sequence number for the bridge session. | Numeric sequence value, present on every observed message. | true |
| Session ID | `sessionId` | Links the record back to the source transcript session. | UUID-style session identifier, present on every observed message. | false |
| Type | `type` | Routes the raw record into its top-level message category. | Constant string value `bridge-session`, present on every observed message. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Bridge Session ID | `bridgeSessionId` | Use the raw `bridgeSessionId` value. | Compact copyable identifier. |
| Last Sequence Num | `lastSequenceNum` | Use the raw `lastSequenceNum` value. | Right-aligned numeric scalar. |

## Card Design

```text
+--------------------------------------------------------------------------+
| [Bridge Session] [Raw Event]                                   [pin] [x] |
+--------------------------------------------------------------------------+
|                         Content | Metadata | Raw                         |
+--------------------------------------------------------------------------+
| Bridge Session ID        <bridgeSessionId>                               |
| Last Sequence Num        <lastSequenceNum>                               |
+--------------------------------------------------------------------------+
```
