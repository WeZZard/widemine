# User / Tool Result

## Fields
| Field | Purpose | Contents | Key | Summary |
|---|---|---|---|---|
| `content` | Primary tool result payload shown in the navigation summary and card body. | Required in 76 shapes; count 43562; string count 41724; array count 1838; max string length 87555; max array items 24. | true | true |
| `tool_use_id` | Pairs the result with the originating assistant tool call. | Required in 76 shapes; count 43562; string; max length 30; values use the `toolu_...` form. | true | false |
| `is_error` | Explicit tool result error flag when the producer supplies one. | Optional; present in 56 shapes; count 22118; boolean. Absence is unknown, not success. | true | false |
| `type` | Raw subtype discriminator for routing this message as a tool result. | Required in 76 shapes; count 43562; string; observed value `tool_result`. | false | false |
| `content[]` | Typed content item container for array-form results. | Present in 6 shapes; count 2599; object items. | false | false |
| `content[].type` | Typed content block discriminator used to choose text, tool-name, or source rendering. | Present in 6 shapes; count 2599; string; max length 14. | false | false |
| `content[].text` | Text body carried by a typed content item. | Present in 4 shapes; count 1819; string; max length 48645. | true | false |
| `content[].text.$json` | Parsed JSON view of a typed text item. | Present in 2 shapes; count 140; object. Keep with parsed detail or raw views. | false | false |
| `content[].tool_name` | Tool name carried by a typed content item. | Present in 1 shape; count 682; string; max length 68. | true | false |
| `content[].source` | Source container for embedded rich result content. | Present in 3 shapes; count 98; object. Child fields define the rendered source. | false | false |
| `content[].source.media_type` | Media type for embedded rich result content. | Present in 3 shapes; count 98; string; max length 10. | true | false |
| `content[].source.data` | Embedded rich result data. | Present in 3 shapes; count 98; string; max length 551108. | true | false |
| `content[].source.type` | Embedded source encoding discriminator. | Present in 3 shapes; count 98; string; max length 6. | false | false |
| `content.$json` | Parsed structured view of string content. | Present in 68 shapes; count 174; object or array; max array items 20. Treat as a derived content view, not a key field. | false | false |
| `content.$json[]` | Parsed JSON array items when the result body is an array. | Present in 6 shapes; count 55; object or string; max string length 20. | false | false |
| `content.$json.$defs` | JSON schema definitions object inside parsed content. | Present in 3 shapes; count 5; object. | false | false |
| `content.$json.$defs.executor` | Executor schema definition inside parsed content. | Present in 3 shapes; count 5; object. | false | false |
| `content.$json.$defs.task` | Task schema definition inside parsed content. | Present in 3 shapes; count 5; object. | false | false |
| `content.$json.$id` | JSON schema identifier inside parsed content. | Present in 3 shapes; count 5; string; max length 89. | false | false |
| `content.$json.$schema` | JSON schema URL inside parsed content. | Present in 10 shapes; count 12; string; max length 57. | false | false |
| `content.$json.additionalProperties` | JSON schema additional-properties flag inside parsed content. | Present in 3 shapes; count 5; boolean. | false | false |
| `content.$json.properties` | JSON schema properties object inside parsed content. | Present in 8 shapes; count 10; object. | false | false |
| `content.$json.properties.nodes` | JSON schema property definition for nodes. | Present in 3 shapes; count 5; object. | false | false |
| `content.$json.properties.version` | JSON schema property definition for version. | Present in 3 shapes; count 5; object. | false | false |
| `content.$json.required` | JSON schema required-field list inside parsed content. | Present in 7 shapes; count 9; array; max items 4. | false | false |
| `content.$json.required[]` | JSON schema required-field list item. | Present in 7 shapes; count 22; string; max length 9. | false | false |
| `content.$json.title` | Title field inside parsed content or parsed schema content. | Present in 9 shapes; count 12; string; max length 40. | false | false |
| `content.$json.type` | Type field inside parsed content or parsed schema content. | Present in 16 shapes; count 24; string; max length 9. | false | false |
| `content.$json.status` | Status field inside parsed content. | Present in 5 shapes; count 11; string; max length 8. | false | false |
| `content.$json.task` | Task field inside parsed content. | Present in 3 shapes; count 8; string; max length 27. | false | false |
| `content.$json.task_id` | Task identifier field inside parsed content. | Present in 1 shape; count 21; string; max length 17. | false | false |
| `content.$json.task_type` | Task type field inside parsed content. | Present in 1 shape; count 21; string; max length 11. | false | false |
| `content.$json.command` | Command field inside parsed content. | Present in 1 shape; count 21; string; max length 781. | false | false |
| `content.$json.message` | Message field inside parsed content. | Present in 2 shapes; count 22; object or string; max string length 820. | false | false |
| `content.$json.screenshot_file_path` | Screenshot file path field inside parsed content. | Present in 1 shape; count 22; string; max length 172. | false | false |
| `content.$json.screenshot_height` | Screenshot height field inside parsed content. | Present in 1 shape; count 22; number. | false | false |
| `content.$json.screenshot_width` | Screenshot width field inside parsed content. | Present in 1 shape; count 22; number. | false | false |
| `content.$json.tree_markdown` | Tree markdown field inside parsed content. | Present in 2 shapes; count 31; string; max length 10511. | false | false |
| `content.$json.window_id` | Window identifier field inside parsed content. | Present in 2 shapes; count 31; number. | false | false |
| `content.$json.windows` | Windows array field inside parsed content. | Present in 3 shapes; count 14; array; max items 88. | false | false |
| `content.$json.windows[]` | Window item inside parsed content. | Present in 1 shape; count 56; object. | false | false |
| `content.$json.current_space_id` | Current space identifier field inside parsed content. | Present in 2 shapes; count 12; null. | false | false |
| `content.$json.active` | Active flag inside parsed content. | Present in 1 shape; count 9; boolean. | false | false |
| `content.$json.session` | Session field inside parsed content. | Present in 2 shapes; count 10; string; max length 36. | false | false |
| `content.$json.enabled` | Enabled flag inside parsed content. | Present in 2 shapes; count 8; boolean. | false | false |
| `content.$json.recording` | Recording flag inside parsed content. | Present in 2 shapes; count 8; boolean. | false | false |
| `content.$json.video_active` | Video active flag inside parsed content. | Present in 2 shapes; count 8; boolean. | false | false |
| `content.$json.last_error` | Last error field inside parsed content. | Present in 2 shapes; count 8; null. | false | false |
| `content.$json.name` | Name field inside parsed content. | Present in 20 shapes; count 30; string; max length 54. | false | false |
| `content.$json.version` | Version field inside parsed content. | Present in 13 shapes; count 19; string; max length 12. | false | false |
| `content.$json.description` | Description field inside parsed content. | Present in 19 shapes; count 27; string; max length 833. | false | false |
| `content.$json.repository` | Repository field inside parsed content. | Present in 5 shapes; count 7; object or string; max string length 67. | false | false |
| `content.$json.url` | URL field inside parsed content. | Present in 1 shape; count 1; string; max length 31. | false | false |
| `content.$json.homepage` | Homepage field inside parsed content. | Present in 4 shapes; count 6; string; max length 67. | false | false |
| `content.$json.author` | Author object inside parsed content. | Present in 5 shapes; count 7; object. | false | false |
| `content.$json.license` | License field inside parsed content. | Present in 5 shapes; count 7; string; max length 14. | false | false |
| `content.$json.keywords` | Keywords array inside parsed content. | Present in 4 shapes; count 6; array; max items 7. | false | false |
| `content.$json.keywords[]` | Keyword item inside parsed content. | Present in 4 shapes; count 31; string; max length 14. | false | false |
| `content.$json.findings` | Findings field inside parsed content. | Present in 2 shapes; count 2; string; max length 246. | false | false |
| `content.$json.verdict` | Verdict field inside parsed content. | Present in 2 shapes; count 2; string; max length 4. | false | false |
| `content.$json.summary` | Summary field inside parsed content. | Present in 1 shape; count 2; string; max length 76. | false | false |
| `content.$json.focus` | Focus field inside parsed content. | Present in 2 shapes; count 5; string; max length 48. | false | false |
| `content.$json.acceptance_criteria` | Acceptance criteria array inside parsed content. | Present in 2 shapes; count 3; array; max items 7. | false | false |
| `content.$json.acceptance_criteria[]` | Acceptance criteria item inside parsed content. | Present in 2 shapes; count 13; string; max length 193. | false | false |
| `content.$json.deps` | Dependency list inside parsed content. | Present in 2 shapes; count 3; array; max items 2. | false | false |
| `content.$json.deps[]` | Dependency list item inside parsed content. | Present in 1 shape; count 2; string; max length 12. | false | false |
| `content.$json.groups` | Groups array inside parsed content. | Present in 1 shape; count 8; array; max items 104. | false | false |
| `content.$json.groups[]` | Group item inside parsed content. | Present in 1 shape; count 80; object. | false | false |
| `content.$json.nodes` | Nodes array inside parsed content. | Present in 2 shapes; count 4; array; max items 12. | false | false |
| `content.$json.nodes[]` | Node item inside parsed content. | Present in 2 shapes; count 21; object. | false | false |
| `content.$json.inputs` | Inputs array inside parsed content. | Present in 1 shape; count 3; array; max items 4. | false | false |
| `content.$json.inputs[]` | Input item inside parsed content. | Present in 1 shape; count 6; string; max length 15. | false | false |
| `content.$json.outputs` | Outputs array inside parsed content. | Present in 1 shape; count 3; array; max items 3. | false | false |
| `content.$json.outputs[]` | Output item inside parsed content. | Present in 1 shape; count 5; string; max length 15. | false | false |

## Derived Car Form Content
| Field | Source Field | Contents |
|---|---|---|
| Result Content | `content` | Raw `content` value. |
| Tool Use ID | `tool_use_id` | Raw `tool_use_id` value. |
| Error | `is_error` | Raw `is_error` value when present. |
| Text Block | `content[].text` | Raw `text` value for each typed content item. |
| Tool Name | `content[].tool_name` | Raw `tool_name` value for each typed content item. |
| Media Type | `content[].source.media_type` | Raw `media_type` value for each source item. |
| Media Data | `content[].source.data` | Raw `data` value for each source item. |

## Message Navigation Item Design
```text
+--------------------------------------------------------------------------------+
| User / Tool Result                                                14:32:07      |
| toolu_01Wve5tCfHujvEp8s7NUcz1s | is_error=false | {"defaultBranchRef":...     |
+--------------------------------------------------------------------------------+
  category / subtype                                         spacer  time
  summary contents
```

Preview rules:
- Line 1 is always `User / Tool Result`, flexible spacer, then the timestamp.
- Line 2 starts with `tool_use_id`, then `is_error=<value>` when present, then the first meaningful raw `content` segment.
- For array-form `content`, use the first `content[].text`; if no text exists, use `content[].tool_name`; if the item is media, use `content[].source.media_type` plus a compact data-size label.
- If `is_error` is missing, omit it rather than displaying success.
- Preserve tool output wording and line order; collapse whitespace only for the one-line navigation summary.

## Message Card Design
```text
+------------------------------------------------------------------------------------------------+
| User / Tool Result                                                               14:32:07 [Raw] |
+------------------------------------------------------------------------------------------------+
| Content Form                                                                                   |
|                                                                                                |
|  Result Details                                                                                |
|  +--------------+-----------------------------------------------------------------------------+ |
|  | Tool Use ID  | toolu_01Wve5tCfHujvEp8s7NUcz1s                                             | |
|  | Error        | false                                                                       | |
|  | Type         | tool_result                                                                 | |
|  +--------------+-----------------------------------------------------------------------------+ |
|                                                                                                |
|  Result Content                                                                                |
|  +------------------------------------------------------------------------------------------+  |
|  | {"defaultBranchRef":{"name":"main"},"description":"Every issue has an answer.",...        |  |
|  | Long stdout, stderr, command output, persisted-output notices, or JSON strings wrap here. |  |
|  +------------------------------------------------------------------------------------------+  |
|                                                                                                |
|  Typed Content Items                                                                           |
|  +----+------------+------------------------------+----------------------+-------------------+ |
|  | #  | Type       | Text                         | Tool Name            | Source            | |
|  | 1  | text       | <content[].text>             | <content[].tool_name>| +---------------+ | |
|  |    |            |                              |                      | | Media Type   | | |
|  |    |            |                              |                      | | Data         | | |
|  |    |            |                              |                      | +---------------+ | |
|  +----+------------+------------------------------+----------------------+-------------------+ |
|                                                                                                |
|  Parsed JSON Body                                                                              |
|  +----------------------+-------------------------------------------------------------------+ |
|  | status/task/name/... | values from content.$json children                                | |
|  | arrays               | +---------------- nested table for content.$json[] / windows[] ---+ | |
|  |                      | | # | Field values preserved from the parsed payload               | | |
|  |                      | +---------------------------------------------------------------+ | |
|  +----------------------+-------------------------------------------------------------------+ |
|                                                                                                |
|  Raw opens formatted raw JSON for this timeline item; Copy JSON copies the raw event. Parsed   |
|  JSON is a convenience view of `content`, while the raw `content` remains the source of truth.  |
+------------------------------------------------------------------------------------------------+
```
