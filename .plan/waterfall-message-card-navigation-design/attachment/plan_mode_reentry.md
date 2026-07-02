# Attachment / Plan Mode Reentry

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `planFilePath` | Provides the markdown plan path restored when plan mode is re-entered. | Required string; observed in 64 messages; max length 79; samples are `.md` files under `/Users/wezzard/.claude/plans/`. | true | true |
| `type` | Attachment subtype discriminator for routing and badges. | Required constant string `plan_mode_reentry`. | false | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Plan File Path | Absolute path string from `planFilePath`. |

## Message Navigation Item Design

```text
Attachment / Plan Mode Reentry ........................................ 14:32:07
/Users/wezzard/.claude/plans/cached-skipping-moth.md
```

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [Plan Mode Reentry]  14:32:07  agent/path   [Raw] [Copy JSON]  |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
|  Plan Mode                                                                     |
|  +----------------+---------------------------------------------------------+  |
|  | Plan File Path | /Users/wezzard/.claude/plans/cached-skipping-moth.md    |  |
|  +----------------+---------------------------------------------------------+  |
|                                                                                |
|  No array fields are present. Raw button opens formatted raw JSON for this     |
|  timeline item; Copy JSON copies the raw payload. Use message typography and   |
|  smaller balanced monospace for the plan path.                                 |
+--------------------------------------------------------------------------------+
```
