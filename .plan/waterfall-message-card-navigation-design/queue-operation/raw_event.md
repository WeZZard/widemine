# Queue Operation

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| content | Queued payload or command content attached to the operation when present. | string; present on content-bearing events; sample `/model` | true | false |
| operation | Queue action performed. | string; samples `enqueue`, `dequeue`, `remove` | true | true |
| sessionId | Session identifier for the queue operation. | UUID string | true | false |
| timestamp | Event time for ordering and display. | ISO 8601 string | true | false |
| type | Raw event discriminator. | constant `queue-operation` | false | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Operation | `{operation}` |
| Content | `{content}` |
| Session ID | `{sessionId}` |
| Time | `{timestamp}` |

## Message Navigation Item Design

Use `Queue Operation` as the first-level category. This kind has no second-level category.

```text
Queue Operation ................................................ {time}
{operation} {content}
```

When `content` is absent, line 2 contains only `{operation}`.

## Message Card Design

Render the card with a compact title bar and a direct content form. No array fields are present in the compiled shapes, so no nested array table is required.

```text
+-- o Queue Operation ---------------- {time} -- main -- Raw -- Copy JSON --+
| Operation   {operation}                                                    |
| Content     {content}                                                      |
| Session ID  {sessionId}                                                    |
| Time        {timestamp}                                                    |
+-----------------------------------------------------------------------------+
```
