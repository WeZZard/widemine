# Agent Name

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| agentName | Agent name recorded by the event and shown as the primary result. | string; count 1761; max length 42; samples `reddit-demand-product-driver`, `reddit-driven-product-discovery`, `observability-milestone-two` | true | true |
| sessionId | Session identifier used to associate the agent name with its transcript. | UUID string; count 1761 | true | false |
| type | Raw event discriminator. | constant `agent-name` | false | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Agent Name | `{agentName}` |
| Session ID | `{sessionId}` |

## Message Navigation Item Design

Use `Agent Name` as the first-level category. This kind has no second-level category.

```text
Agent Name ................................................ {time}
{agentName}
```

## Message Card Design

Render the card with a compact title bar and a direct content form. No array fields are present in the compiled shapes, so no nested array table is required.

```text
+-- o Agent Name ----------------- {time} -- main -- Raw -- Copy JSON --+
| Agent Name  {agentName}                                                |
| Session ID  {sessionId}                                                |
+------------------------------------------------------------------------+
```
