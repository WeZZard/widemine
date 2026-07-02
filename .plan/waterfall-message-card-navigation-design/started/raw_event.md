# Started

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| agentId | Identifies the workflow agent associated with the started event. | string; count 2120; max length 17; sample `ab135a74496f0c8ff` | true | true |
| key | Provides the stable start event key paired with the workflow agent. | string; count 2120; max length 67; sample `v2:c39c29407491b50f9b0802988726512a32f6e73c6f6d3ba57f77ce91ffe88c4f` | true | false |
| type | Raw event discriminator. | constant `started` | false | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Agent ID | `{agentId}` |
| Key | `{key}` |

## Message Navigation Item Design

Use `Started` as the first-level category. This kind has no second-level category.

```text
Started ................................................... {time}
{agentId}
```

## Message Card Design

Render the card with a compact title bar and a direct content form. No array fields are present in the compiled shapes, so no nested array table is required.

```text
+-- o Started -------------------- {time} -- main -- Raw -- Copy JSON --+
| Agent ID  {agentId}                                                    |
| Key       {key}                                                        |
+------------------------------------------------------------------------+
```
