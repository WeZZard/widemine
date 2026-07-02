# Bridge Session

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| bridgeSessionId | Identifies the bridge session represented by the event. | string; count 387; max length 28; sample `cse_01Lb3etRE9ibVqZeKy1doMU6` | true | true |
| lastSequenceNum | Records the last sequence number known for the bridge session. | number; count 387; samples `0`, `16`, `168` | true | false |
| sessionId | Links the bridge session event to the transcript session. | UUID string; count 387; max length 36; sample `eba215db-ed3a-4bd1-a7bd-10f20a2d85cf` | true | false |
| type | Raw event discriminator. | constant `bridge-session` | false | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Bridge Session ID | `{bridgeSessionId}` |
| Last Sequence Number | `{lastSequenceNum}` |
| Session ID | `{sessionId}` |

## Message Navigation Item Design

Use `Bridge Session` as the first-level category. This kind has no second-level category.

```text
Bridge Session ............................................. {time}
{bridgeSessionId}
```

## Message Card Design

Render the card with a compact title bar and a direct content form. No array fields are present in the compiled shape, so no nested array table is required.

```text
+-- o Bridge Session ------------- {time} -- main -- Raw -- Copy JSON --+
| Bridge Session ID     {bridgeSessionId}                                |
| Last Sequence Number  {lastSequenceNum}                                |
| Session ID            {sessionId}                                      |
+------------------------------------------------------------------------+
```
