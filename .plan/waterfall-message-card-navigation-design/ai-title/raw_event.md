# AI Title

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| aiTitle | Session title text shown as the event result and preview. | string; count 3386; max length 66; sample `Clone readycheck repositories locally` | true | true |
| sessionId | Session identifier used to associate the title with its transcript. | UUID string; count 3386 | true | false |
| type | Raw event discriminator. | constant `ai-title` | false | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| AI Title | `{aiTitle}` |
| Session ID | `{sessionId}` |

## Message Navigation Item Design

Use `AI Title` as the first-level category. This kind has no second-level category.

```text
AI Title .................................................. {time}
{aiTitle}
```

## Message Card Design

Render the card with a compact title bar and a direct content form. No array fields are present in the compiled shapes, so no nested array table is required.

```text
+-- o AI Title ------------------- {time} -- main -- Raw -- Copy JSON --+
| AI Title    {aiTitle}                                                  |
| Session ID  {sessionId}                                                |
+------------------------------------------------------------------------+
```
