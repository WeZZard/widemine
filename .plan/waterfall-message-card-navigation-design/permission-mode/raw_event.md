# Permission Mode

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| permissionMode | Permission mode value recorded by the event and shown as the primary result. | string; count 2936; max length 17; samples `bypassPermissions`, `auto`, `plan`, `default` | true | true |
| sessionId | Session identifier used to associate the permission mode with its transcript. | UUID string; count 2936 | true | false |
| type | Raw event discriminator. | constant `permission-mode` | false | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Permission Mode | `{permissionMode}` |
| Session ID | `{sessionId}` |

## Message Navigation Item Design

Use `Permission Mode` as the first-level category. This kind has no second-level category.

```text
Permission Mode ............................................. {time}
{permissionMode}
```

## Message Card Design

Render the card with a compact title bar and a direct content form. No array fields are present in the compiled shapes, so no nested array table is required.

```text
+-- o Permission Mode ------------ {time} -- main -- Raw -- Copy JSON --+
| Permission Mode  {permissionMode}                                      |
| Session ID       {sessionId}                                           |
+------------------------------------------------------------------------+
```
