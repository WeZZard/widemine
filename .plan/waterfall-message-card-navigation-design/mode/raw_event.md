# Mode

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| mode | Mode status value shown as the event result and preview. | string; count 2865; max length 6; sample `normal` | true | true |
| sessionId | Session identifier used to associate the mode event with its transcript. | UUID string; count 2865 | true | false |
| type | Raw event discriminator. | constant `mode` | false | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Mode | `{mode}` |
| Session ID | `{sessionId}` |

## Message Navigation Item Design

Use `Mode` as the first-level category. This kind has no second-level category.

```text
Mode ....................................................... {time}
{mode}
```

## Message Card Design

Render the card with a compact title bar and a direct content form. No array fields are present in the compiled shapes, so no nested array table is required.

```text
+-- o Mode ----------------------- {time} -- main -- Raw -- Copy JSON --+
| Mode        {mode}                                                     |
| Session ID  {sessionId}                                                |
+------------------------------------------------------------------------+
```
