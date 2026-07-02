# Attachment / Plan Mode Exit

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `planExists` | Indicates whether the plan file still exists when plan mode exits. | Required boolean; observed in 138 messages; samples include `false` and `true`. | true | false |
| `planFilePath` | Absolute path for the plan file associated with the plan-mode exit. | Required string; observed in 138 messages; max length 85; samples are `.md` files under `/Users/wezzard/.claude/plans/`. | true | true |
| `type` | Attachment subtype discriminator. | Required constant string `plan_mode_exit`; rendered through the Plan Mode Exit badge. | false | false |

## Derived Car Form Content

| Field | Source Field | Contents |
| --- | --- | --- |
| Plan Exists | `planExists` | Required boolean value. |
| Plan File Path | `planFilePath` | Required absolute `.md` plan path. |

## Message Navigation Item Design

```text
Attachment / Plan Mode Exit ........................................... 14:32:07
Plan file: /Users/wezzard/.claude/plans/cached-skipping-moth.md
```

Use the attachment-teal tone and render both category levels as full badges where the navigation component supports badges. The second line is the summary line from `planFilePath`; middle-truncate the path only when needed to preserve the filename. If `planFilePath` is unavailable, render `Plan file: unknown`.

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [Plan Mode Exit]  14:32:07  agent/path      [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Plan Mode Exit                                                                 |
| +----------------+----------------------------------------------------------+  |
| | Plan Exists    | false                                                    |  |
| | Plan File Path | /Users/wezzard/.claude/plans/cached-skipping-moth.md     |  |
| +----------------+----------------------------------------------------------+  |
|                                                                                |
| No array fields are present. Raw button opens formatted raw JSON for this      |
| timeline item; Copy JSON copies the raw payload. Use message typography and    |
| smaller balanced monospace for the plan path.                                  |
+--------------------------------------------------------------------------------+
```
