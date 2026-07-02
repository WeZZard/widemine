# Last Prompt

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| lastPrompt | Primary prompt text recorded by the event. | string; present on prompt-bearing records; sample `find readycheck-dev/readycheck and readycheck-dev/readycheck-evals with gh. clone them to local` | true | true |
| leafUuid | Transcript leaf identifier used to anchor the prompt record, especially when prompt text is absent. | UUID string | true | false |
| sessionId | Session identifier used to associate the prompt record with its transcript. | UUID string | true | false |
| type | Raw event discriminator. | constant `last-prompt` | false | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Last Prompt | `{lastPrompt}` |
| Leaf UUID | `{leafUuid}` |
| Session ID | `{sessionId}` |

## Message Navigation Item Design

Use `Last Prompt` as the first-level category. This kind has no second-level category.

```text
Last Prompt ................................................ {time}
{lastPrompt}
```

When `lastPrompt` is absent, keep the same two-line layout and render line 2 as `leaf {leafUuid} session {sessionId}`.

## Message Card Design

Render the card with a compact title bar and a direct content form. No array fields are present in the compiled shapes, so no nested array table is required.

```text
+-- o Last Prompt ----------------- {time} -- main -- Raw -- Copy JSON --+
| Last Prompt  {lastPrompt}                                               |
| Leaf UUID    {leafUuid}                                                 |
| Session ID   {sessionId}                                                |
+--------------------------------------------------------------------------+
```
