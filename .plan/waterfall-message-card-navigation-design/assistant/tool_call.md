# Assistant / Tool Call

## Fields
| Field | Purpose | Contents | Key | Summary |
|---|---|---|---|---|
| `type` | Raw block subtype discriminator. | Required string; 43,599 observed; constant `tool_use`; rendered through the Assistant / Tool Call badges. | false | false |
| `name` | Visible tool name and primary summary anchor. | Required string; 43,599 observed; common values include `Bash`, `Read`, `Edit`, `Write`, `StructuredOutput`, `Agent`, `WebFetch`, `WebSearch`, `Workflow`, and MCP tool names. | true | true |
| `id` | Tool-call identifier used to correlate the call with its result. | Required string; 43,599 observed; max length 30; sample shape `toolu_...`. | true | false |
| `caller` | Caller metadata container. | Required object; 43,599 observed. | false | false |
| `caller.type` | Caller routing marker. | Required string; 43,599 observed; sample `direct`. | false | false |
| `input` | Tool-specific argument container. | Required object; 43,599 observed; body branches by `name` and the available child fields. | false | false |
| `input.command` | Shell command or command-like argument. | Optional string; 21,692 observed; max length 40,282; common on `Bash`. | true | false |
| `input.description` | Human-authored description for a command, subagent, task, or workflow. | Optional string; 14,251 observed; max length 276. | true | false |
| `input.file_path` | File path target for read, write, edit, or file-oriented tools. | Optional string; 15,247 observed; max length 188. | true | false |
| `input.old_string` | Text to replace for edit-like tools. | Optional string; 2,999 observed; max length 14,884. | true | false |
| `input.new_string` | Replacement text for edit-like tools. | Optional string; 2,999 observed; max length 17,128. | true | false |
| `input.replace_all` | Edit replacement mode. | Optional bool; 2,999 observed. | true | false |
| `input.limit` | Read, search, or output limit. | Optional number or string; 2,377 observed. | true | false |
| `input.offset` | Read offset or coordinate-like offset. | Optional number or array; 1,699 observed. | true | false |
| `input.offset[]` | Offset array item. | Optional number; 58 observed. | true | false |
| `input.timeout` | Tool timeout. | Optional number or string; 1,517 observed. | true | false |
| `input.timeout_ms` | Tool timeout in milliseconds. | Optional number; 148 observed. | true | false |
| `input.run_in_background` | Background execution flag. | Optional bool; 848 observed. | true | false |
| `input.prompt` | Prompt sent to a web, agent, fetch, or planning tool. | Optional string or bool; 2,122 observed; max length 16,069. | true | false |
| `input.url` | URL target. | Optional string; 922 observed; max length 130. | true | false |
| `input.query` | Search, window-state, or tool query. | Optional string; 1,152 observed; max length 220. | true | false |
| `input.content` | Written content or structured output body. | Optional string; 1,843 observed; max length 40,673. | true | false |
| `input.content.$json` | Parsed mirror of `input.content` when the content is JSON. | Optional object or array; 1,187 observed; raw-derived support field. | false | false |
| `input.content.$json[]` | Parsed JSON array item. | Optional object; 68 observed. | false | false |
| `input.content.$json.$schema` | Parsed JSON schema URL. | Optional string; 3 observed. | false | false |
| `input.content.$json.$defs` | Parsed JSON schema definitions. | Optional object; 1 observed. | false | false |
| `input.content.$json.$id` | Parsed JSON schema identifier. | Optional string; 1 observed. | false | false |
| `input.content.$json._note` | Parsed JSON note field. | Optional string; 1 observed. | false | false |
| `input.content.$json.additionalProperties` | Parsed JSON schema additional-properties flag. | Optional bool; 1 observed. | false | false |
| `input.content.$json.author` | Parsed JSON author field. | Optional value; 1 observed. | false | false |
| `input.content.$json.batch` | Parsed JSON batch number. | Optional number; 1 observed. | false | false |
| `input.content.$json.capabilities` | Parsed JSON capabilities field. | Optional value; 2 observed. | false | false |
| `input.content.$json.compilerOptions` | Parsed JSON compiler options field. | Optional object; 1 observed. | false | false |
| `input.content.$json.dependencies` | Parsed JSON dependencies field. | Optional object; 2 observed. | false | false |
| `input.content.$json.description` | Parsed JSON description field. | Optional string; 3 observed. | false | false |
| `input.content.$json.devDependencies` | Parsed JSON dev dependencies field. | Optional object; 1 observed. | false | false |
| `input.content.$json.engines` | Parsed JSON engines field. | Optional object; 1 observed. | false | false |
| `input.content.$json.function` | Parsed JSON function field. | Optional object; 7 observed. | false | false |
| `input.content.$json.homepage` | Parsed JSON homepage field. | Optional string; 1 observed. | false | false |
| `input.content.$json.include` | Parsed JSON include field. | Optional value; 1 observed. | false | false |
| `input.content.$json.inputs` | Parsed JSON inputs field. | Optional value; 1 observed. | false | false |
| `input.content.$json.interface` | Parsed JSON interface field. | Optional value; 1 observed. | false | false |
| `input.content.$json.keywords` | Parsed JSON keywords field. | Optional value; 1 observed. | false | false |
| `input.content.$json.license` | Parsed JSON license field. | Optional string; 1 observed. | false | false |
| `input.content.$json.name` | Parsed JSON name field. | Optional string; 5 observed. | false | false |
| `input.content.$json.nodes` | Parsed JSON node array. | Optional array; 55 observed. | false | false |
| `input.content.$json.outputs` | Parsed JSON outputs field. | Optional value; 1 observed. | false | false |
| `input.content.$json.plan_file` | Parsed JSON plan file field. | Optional string; 25 observed. | false | false |
| `input.content.$json.private` | Parsed JSON private flag. | Optional bool; 1 observed. | false | false |
| `input.content.$json.properties` | Parsed JSON schema properties field. | Optional object; 1 observed. | false | false |
| `input.content.$json.provider` | Parsed JSON provider field. | Optional value; 1 observed. | false | false |
| `input.content.$json.providers` | Parsed JSON providers field. | Optional value; 1 observed. | false | false |
| `input.content.$json.renames` | Parsed JSON rename array. | Optional array; 1,085 observed. | false | false |
| `input.content.$json.repository` | Parsed JSON repository field. | Optional string; 1 observed. | false | false |
| `input.content.$json.required` | Parsed JSON required field. | Optional value; 1 observed. | false | false |
| `input.content.$json.scripts` | Parsed JSON scripts field. | Optional object; 1 observed. | false | false |
| `input.content.$json.skills` | Parsed JSON skills path. | Optional string; 1 observed. | false | false |
| `input.content.$json.title` | Parsed JSON title field. | Optional string; 1 observed. | false | false |
| `input.content.$json.type` | Parsed JSON type field. | Optional string; 10 observed. | false | false |
| `input.content.$json.version` | Parsed JSON version field. | Optional number or string; 56 observed. | false | false |
| `input.content.$json.variables` | Parsed JSON variables object. | Optional object; 25 observed. | false | false |
| `input.content.$json.written` | Parsed JSON written count. | Optional number; 1 observed. | false | false |
| `input.args` | Argument string for workflow, monitor, or plugin-style calls. | Optional string; 169 observed; max length 21,208. | true | false |
| `input.args.$json` | Parsed mirror of `input.args` when the args value is JSON. | Optional object; 33 observed; raw-derived support field. | false | false |
| `input.args.$json.batches` | Parsed args batch count. | Optional number; 9 observed. | false | false |
| `input.args.$json.clusterName` | Parsed args cluster name. | Optional string; 2 observed. | false | false |
| `input.args.$json.doneSubstantive` | Parsed args completed substantive count. | Optional number; 1 observed. | false | false |
| `input.args.$json.gbytes` | Parsed args byte budget. | Optional number; 8 observed. | false | false |
| `input.args.$json.gcount` | Parsed args group count. | Optional number; 8 observed. | false | false |
| `input.args.$json.groups` | Parsed args group array. | Optional array; 13 observed. | false | false |
| `input.args.$json.levels` | Parsed args level list. | Optional array; 2 observed. | false | false |
| `input.args.$json.maxBytes` | Parsed args byte limit. | Optional number; 7 observed. | false | false |
| `input.args.$json.maxM` | Parsed args module limit. | Optional number; 8 observed. | false | false |
| `input.args.$json.modules` | Parsed args module set. | Optional object or array; 2 observed. | false | false |
| `input.args.$json.nodePath` | Parsed args node path. | Optional string; 8 observed. | false | false |
| `input.args.$json.order` | Parsed args order field. | Optional array; 2 observed. | false | false |
| `input.args.$json.remainingSubstantive` | Parsed args remaining substantive count. | Optional number; 1 observed. | false | false |
| `input.args.$json.repoAbs` | Parsed args repository path. | Optional string; 24 observed. | false | false |
| `input.args.$json.totalSubstantive` | Parsed args total substantive count. | Optional number; 1 observed. | false | false |
| `input.args.$json.totalTrivial` | Parsed args total trivial count. | Optional number; 1 observed. | false | false |
| `input.args.$json.waveDir` | Parsed args wave directory. | Optional string; 9 observed. | false | false |
| `input.$FUNCTION_NAME` | Parsed function-name helper field. | Optional string; 2 observed; raw-derived support field. | false | false |
| `input.modules` | Module payload container. | Optional array or object; 648 observed. | true | false |
| `input.modules[]` | Repeated module payload item. | Optional object; 1,687 observed. | true | false |
| `input.modules[].id` | Module identifier. | Optional string; 1,687 observed. | true | false |
| `input.modules[].newModuleName` | Proposed module name. | Optional string; 1,687 observed. | true | false |
| `input.modules[].moduleSummary` | Module summary text. | Optional string; 1,687 observed; max length 1,825. | true | false |
| `input.modules[].rewrittenSource` | Rewritten module source. | Optional string; 1,685 observed; max length 115,633. | true | false |
| `input.modules[].globalRenames` | Module-local rename array. | Optional array; 1,686 observed. | true | false |
| `input.modules[].knownNames` | Module known-name map. | Optional object; 3 observed. | true | false |
| `input.modules.modules` | Nested modules container. | Optional array; 3 observed. | true | false |
| `input.modules.modules[]` | Nested module item. | Optional object; 9 observed. | true | false |
| `input.globalRenames` | Global rename array. | Optional array; 13 observed. | true | false |
| `input.globalRenames[]` | Repeated global rename item. | Optional object; 36 observed. | true | false |
| `input.globalRenames[].doc` | Rename documentation. | Optional string; 36 observed. | true | false |
| `input.globalRenames[].kind` | Rename kind. | Optional string; 36 observed. | true | false |
| `input.globalRenames[].new` | New symbol name. | Optional string; 36 observed. | true | false |
| `input.globalRenames[].old` | Old symbol name. | Optional string; 36 observed. | true | false |
| `input.batch` | Structured output batch number. | Optional number; 1,080 observed. | true | false |
| `input.written` | Structured output written count. | Optional number; 1,080 observed. | true | false |
| `input.id` | Input-level identifier used by module or task-like tools. | Optional string; 18 observed. | true | false |
| `input.newModuleName` | Input-level proposed module name. | Optional string; 18 observed. | true | false |
| `input.moduleSummary` | Input-level module summary. | Optional string; 18 observed. | true | false |
| `input.rewrittenSource` | Input-level rewritten source. | Optional string; 18 observed; max length 9,633. | true | false |
| `input.notes` | Notes text. | Optional string; 1 observed; max length 1,360. | true | false |
| `input.verdict` | Verdict value. | Optional string; 1 observed. | true | false |
| `input.subagent_type` | Subagent type requested by agent tools. | Optional string; 1,125 observed. | true | false |
| `input.model` | Model selector for agent or research tools. | Optional string; 456 observed. | true | false |
| `input.allowedPrompts` | Allowed-prompt list for subagent calls. | Optional array; 224 observed. | true | false |
| `input.allowedPrompts[]` | Repeated allowed prompt item. | Optional object; 662 observed. | true | false |
| `input.allowedPrompts[].tool` | Tool allowed for the prompt. | Optional string; 662 observed. | true | false |
| `input.allowedPrompts[].prompt` | Prompt allowed for the tool. | Optional string; 662 observed. | true | false |
| `input.skill` | Skill name for skill invocation tools. | Optional string; 295 observed. | true | false |
| `input.planFilePath` | Plan file path for plan-mode calls. | Optional string; 247 observed. | true | false |
| `input.plan` | Plan content for plan-mode calls. | Optional string; 247 observed; max length 40,673. | true | false |
| `input.questions` | User-question list. | Optional array; 378 observed. | true | false |
| `input.questions[]` | Repeated question item. | Optional object; 516 observed. | true | false |
| `input.questions[].header` | Question header. | Optional string; 516 observed. | true | false |
| `input.questions[].question` | Question text. | Optional string; 516 observed. | true | false |
| `input.questions[].options` | Question option list. | Optional array; 516 observed. | true | false |
| `input.questions[].multiSelect` | Multi-select flag. | Optional bool; 516 observed. | true | false |
| `input.todos` | Todo list container. | Optional array; 30 observed. | true | false |
| `input.todos[]` | Repeated todo item. | Optional object; 192 observed. | true | false |
| `input.todos[].content` | Todo content. | Optional string; 192 observed. | true | false |
| `input.todos[].status` | Todo status. | Optional string; 192 observed. | true | false |
| `input.todos[].activeForm` | Active-form text for the todo. | Optional string; 192 observed. | true | false |
| `input.activeForm` | Active-form text for task tools. | Optional string; 19 observed. | true | false |
| `input.subject` | Task subject. | Optional string; 19 observed. | true | false |
| `input.task_id` | Task identifier. | Optional string; 55 observed. | true | false |
| `input.taskId` | Task identifier variant. | Optional string; 39 observed. | true | false |
| `input.status` | Task status. | Optional string; 39 observed. | true | false |
| `input.block` | Blocking output flag. | Optional bool; 17 observed. | true | false |
| `input.task` | Task identifier or task name. | Optional string; 1 observed. | true | false |
| `input.actions` | GUI or computer-use action list. | Optional array; 12 observed. | true | false |
| `input.actions[]` | Repeated GUI or computer-use action item. | Optional object; 34 observed. | true | false |
| `input.actions[].action` | Action name. | Optional string; 34 observed. | true | false |
| `input.actions[].coordinate` | Action coordinate. | Optional array; 11 observed. | true | false |
| `input.actions[].duration` | Action duration. | Optional number; 6 observed. | true | false |
| `input.actions[].scroll_amount` | Scroll amount for action items. | Optional number; 1 observed. | true | false |
| `input.actions[].scroll_direction` | Scroll direction for action items. | Optional string; 1 observed. | true | false |
| `input.actions[].start_coordinate` | Action start coordinate. | Optional array; 1 observed. | true | false |
| `input.actions[].text` | Typed text for action items. | Optional string; 5 observed. | true | false |
| `input.coordinate` | Single coordinate argument. | Optional array; 22 observed. | true | false |
| `input.coordinate[]` | Single coordinate item. | Optional number; 44 observed. | true | false |
| `input.start_coordinate` | Single start coordinate argument. | Optional array; 6 observed. | true | false |
| `input.start_coordinate[]` | Single start coordinate item. | Optional number; 12 observed. | true | false |
| `input.x` | X coordinate. | Optional number; 10 observed. | true | false |
| `input.y` | Y coordinate. | Optional number; 10 observed. | true | false |
| `input.x1` | Region start X coordinate. | Optional number; 18 observed. | true | false |
| `input.y1` | Region start Y coordinate. | Optional number; 18 observed. | true | false |
| `input.x2` | Region end X coordinate. | Optional number; 18 observed. | true | false |
| `input.y2` | Region end Y coordinate. | Optional number; 18 observed. | true | false |
| `input.region` | Region argument. | Optional array; 20 observed. | true | false |
| `input.region[]` | Region item. | Optional number; 80 observed. | true | false |
| `input.element_index` | GUI element index. | Optional number; 13 observed. | true | false |
| `input.window_id` | GUI window identifier. | Optional number; 76 observed. | true | false |
| `input.pid` | Process identifier for GUI tools. | Optional number; 89 observed. | true | false |
| `input.session` | GUI session identifier. | Optional string; 69 observed. | true | false |
| `input.capture_mode` | GUI capture mode. | Optional string; 30 observed. | true | false |
| `input.screenshot_out_file` | Screenshot output path. | Optional string; 26 observed. | true | false |
| `input.debug_image_out` | Debug image output path. | Optional string; 1 observed. | true | false |
| `input.app` | Application identifier. | Optional string; 10 observed. | true | false |
| `input.apps` | Application list. | Optional array; 73 observed. | true | false |
| `input.apps[]` | Application list item. | Optional string; 93 observed. | true | false |
| `input.bundle_id` | Application bundle identifier. | Optional string; 6 observed. | true | false |
| `input.record_video` | Video recording flag. | Optional bool; 4 observed. | true | false |
| `input.output_dir` | Output directory. | Optional string; 4 observed. | true | false |
| `input.resourceTypes` | Resource type filter. | Optional array; 3 observed. | true | false |
| `input.resourceTypes[]` | Resource type filter item. | Optional string; 11 observed. | true | false |
| `input.uid` | Browser or devtools node UID. | Optional string; 2 observed. | true | false |
| `input.includeSnapshot` | Browser snapshot include flag. | Optional bool; 1 observed. | true | false |
| `input.text` | Text argument. | Optional string; 7 observed. | true | false |
| `input.key` | Key argument. | Optional string; 5 observed. | true | false |
| `input.action` | Single action argument. | Optional string; 4 observed. | true | false |
| `input.type` | Input type selector. | Optional string; 4 observed. | true | false |
| `input.types` | Type list container. | Optional array; 2 observed. | true | false |
| `input.types[]` | Type list item. | Optional string; 2 observed. | true | false |
| `input.title` | Title argument. | Optional string; 3 observed. | true | false |
| `input.name` | Name argument inside input. | Optional string; 3 observed. | true | false |
| `input.value` | Generic value argument. | Optional string; 1 observed. | true | false |
| `input.summary` | Summary text. | Optional string; 5 observed. | true | false |
| `input.reason` | Reason text for verification or access tools. | Optional string; 94 observed. | true | false |
| `input.question` | Single question argument. | Optional string; 1 observed. | true | false |
| `input.pages` | Page range argument. | Optional string; 1 observed. | true | false |
| `input.duration` | Duration argument. | Optional number; 10 observed. | true | false |
| `input.interval` | Polling interval. | Optional number; 1 observed. | true | false |
| `input.until` | Completion condition. | Optional string; 2 observed. | true | false |
| `input.persistent` | Persistent monitor flag. | Optional bool; 159 observed. | true | false |
| `input.on_screen_only` | On-screen-only filter. | Optional bool; 1 observed. | true | false |
| `input.dangerouslyDisableSandbox` | Sandbox-disable flag. | Optional bool; 31 observed. | true | false |
| `input.systemKeyCombos` | System key-combo flag. | Optional bool; 2 observed. | true | false |
| `input.clipboardRead` | Clipboard read permission flag. | Optional bool; 1 observed. | true | false |
| `input.clipboardWrite` | Clipboard write permission flag. | Optional bool; 1 observed. | true | false |
| `input.save_to_disk` | Save-to-disk flag. | Optional bool; 1 observed. | true | false |
| `input.script` | Script content. | Optional string; 1 observed; max length 4,868. | true | false |
| `input.scriptPath` | Script path. | Optional string; 33 observed; max length 114. | true | false |
| `input.scroll_amount` | Single scroll amount argument. | Optional number; 1 observed. | true | false |
| `input.scroll_direction` | Single scroll direction argument. | Optional string; 1 observed. | true | false |
| `input.delaySeconds` | Wakeup delay. | Optional number; 21 observed. | true | false |
| `input.max_results` | Search result count limit. | Optional number; 370 observed. | true | false |
| `input.allowed_domains` | Allowed-domain list. | Optional array; 47 observed. | true | false |
| `input.allowed_domains[]` | Allowed-domain item. | Optional string; 91 observed. | true | false |
| `input.results` | Result list. | Optional array; 5 observed. | true | false |
| `input.results[]` | Repeated result item. | Optional object; 30 observed. | true | false |
| `input.results[].title` | Result title. | Optional string; 30 observed. | true | false |
| `input.results[].url` | Result URL. | Optional string; 30 observed. | true | false |
| `input.results[].snippet` | Result snippet. | Optional string; 30 observed. | true | false |
| `input.results[].relevance` | Result relevance. | Optional string; 30 observed. | true | false |
| `input.claims` | Claim list. | Optional array; 20 observed. | true | false |
| `input.claims[]` | Repeated claim item. | Optional object; 85 observed. | true | false |
| `input.claims[].claim` | Claim text. | Optional string; 85 observed. | true | false |
| `input.claims[].importance` | Claim importance. | Optional string; 85 observed. | true | false |
| `input.claims[].quote` | Supporting quote text. | Optional string; 85 observed. | true | false |
| `input.evidence` | Evidence text. | Optional string; 75 observed. | true | false |
| `input.confidence` | Confidence value. | Optional string; 75 observed. | true | false |
| `input.refuted` | Refuted flag. | Optional bool; 75 observed. | true | false |
| `input.sourceQuality` | Source quality. | Optional string; 20 observed. | true | false |
| `input.publishDate` | Publication date. | Optional string; 20 observed. | true | false |
| `input.counterSource` | Counter-source text. | Optional string; 74 observed. | true | false |
| `input.caveats` | Caveat text. | Optional string; 1 observed; max length 1,581. | true | false |
| `input.findings` | Finding list container. | Optional array; 1 observed. | true | false |
| `input.findings[]` | Repeated finding item. | Optional object; 10 observed. | true | false |
| `input.findings[].claim` | Finding claim. | Optional string; 10 observed. | true | false |
| `input.findings[].evidence` | Finding evidence. | Optional string; 10 observed. | true | false |
| `input.findings[].confidence` | Finding confidence. | Optional string; 10 observed. | true | false |
| `input.findings[].sources` | Finding source list. | Optional array; 10 observed. | true | false |
| `input.findings[].vote` | Finding vote. | Optional string; 10 observed. | true | false |
| `input.angles` | Search-angle list container. | Optional array; 1 observed. | true | false |
| `input.angles[]` | Repeated search angle item. | Optional object; 5 observed. | true | false |
| `input.angles[].label` | Search angle label. | Optional string; 5 observed. | true | false |
| `input.angles[].query` | Search angle query. | Optional string; 5 observed. | true | false |
| `input.angles[].rationale` | Search angle rationale. | Optional string; 5 observed. | true | false |
| `input.issues` | Issue list container. | Optional array; 1 observed. | true | false |
| `input.issues[]` | Repeated issue item. | Optional object; 8 observed. | true | false |
| `input.issues[].detail` | Issue detail. | Optional string; 8 observed. | true | false |
| `input.issues[].kind` | Issue kind. | Optional string; 8 observed. | true | false |
| `input.issues[].module` | Issue module. | Optional string; 8 observed. | true | false |
| `input.issues[].suggestion` | Issue suggestion. | Optional string; 8 observed. | true | false |
| `input.openQuestions` | Open-question list container. | Optional array; 1 observed. | true | false |
| `input.openQuestions[]` | Open-question item. | Optional string; 4 observed. | true | false |
| `input.old_string.$json` | Parsed mirror of `input.old_string` when the old string is JSON. | Optional object; 1 observed; raw-derived support field. | false | false |
| `input.old_string.$json.agent` | Parsed old-string agent field. | Optional string; 1 observed. | false | false |
| `input.old_string.$json.deps` | Parsed old-string dependency field. | Optional array; 1 observed. | false | false |
| `input.old_string.$json.id` | Parsed old-string ID field. | Optional string; 1 observed. | false | false |
| `input.old_string.$json.kind` | Parsed old-string kind field. | Optional string; 1 observed. | false | false |
| `input.old_string.$json.promptTemplate` | Parsed old-string prompt template. | Optional string; 1 observed. | false | false |
| `input.old_string.$json.schema` | Parsed old-string schema field. | Optional object; 1 observed. | false | false |
| `input.__unparsedToolInput` | Fallback container for tool input that could not be parsed into normal fields. | Optional object; 4 observed; internal recovery field. | false | false |
| `input.__unparsedToolInput.len` | Byte or character length for unparsed input. | Optional number; 4 observed; internal recovery field. | false | false |
| `input.__unparsedToolInput.raw` | Raw unparsed input payload. | Optional string; 4 observed; internal recovery field. | false | false |

## Derived Car Form Content
| Field | Source Field | Contents |
|---|---|---|
| Tool Name | `name` | Value of `name`. |
| Tool Call ID | `id` | Value of `id`. |
| Command | `input.command` | Value of `input.command`. |
| Description | `input.description` | Value of `input.description`. |
| File Path | `input.file_path` | Value of `input.file_path`. |
| Old String | `input.old_string` | Value of `input.old_string`. |
| New String | `input.new_string` | Value of `input.new_string`. |
| Replace All | `input.replace_all` | Value of `input.replace_all`. |
| Limit | `input.limit` | Value of `input.limit`. |
| Offset | `input.offset` | Value of `input.offset`. |
| Offset Item | `input.offset[]` | Values of `input.offset[]`. |
| Timeout | `input.timeout` | Value of `input.timeout`. |
| Timeout MS | `input.timeout_ms` | Value of `input.timeout_ms`. |
| Run In Background | `input.run_in_background` | Value of `input.run_in_background`. |
| Prompt | `input.prompt` | Value of `input.prompt`. |
| URL | `input.url` | Value of `input.url`. |
| Query | `input.query` | Value of `input.query`. |
| Content | `input.content` | Value of `input.content`. |
| Args | `input.args` | Value of `input.args`. |
| Modules | `input.modules` | Value of `input.modules`. |
| Module | `input.modules[]` | Values of `input.modules[]`. |
| Module ID | `input.modules[].id` | Values of `input.modules[].id`. |
| Module New Module Name | `input.modules[].newModuleName` | Values of `input.modules[].newModuleName`. |
| Module Summary | `input.modules[].moduleSummary` | Values of `input.modules[].moduleSummary`. |
| Module Rewritten Source | `input.modules[].rewrittenSource` | Values of `input.modules[].rewrittenSource`. |
| Module Global Renames | `input.modules[].globalRenames` | Values of `input.modules[].globalRenames`. |
| Module Known Names | `input.modules[].knownNames` | Values of `input.modules[].knownNames`. |
| Nested Modules | `input.modules.modules` | Value of `input.modules.modules`. |
| Nested Module | `input.modules.modules[]` | Values of `input.modules.modules[]`. |
| Global Renames | `input.globalRenames` | Value of `input.globalRenames`. |
| Global Rename | `input.globalRenames[]` | Values of `input.globalRenames[]`. |
| Global Rename Doc | `input.globalRenames[].doc` | Values of `input.globalRenames[].doc`. |
| Global Rename Kind | `input.globalRenames[].kind` | Values of `input.globalRenames[].kind`. |
| Global Rename New | `input.globalRenames[].new` | Values of `input.globalRenames[].new`. |
| Global Rename Old | `input.globalRenames[].old` | Values of `input.globalRenames[].old`. |
| Batch | `input.batch` | Value of `input.batch`. |
| Written | `input.written` | Value of `input.written`. |
| Input ID | `input.id` | Value of `input.id`. |
| New Module Name | `input.newModuleName` | Value of `input.newModuleName`. |
| Module Summary | `input.moduleSummary` | Value of `input.moduleSummary`. |
| Rewritten Source | `input.rewrittenSource` | Value of `input.rewrittenSource`. |
| Notes | `input.notes` | Value of `input.notes`. |
| Verdict | `input.verdict` | Value of `input.verdict`. |
| Subagent Type | `input.subagent_type` | Value of `input.subagent_type`. |
| Model | `input.model` | Value of `input.model`. |
| Allowed Prompts | `input.allowedPrompts` | Value of `input.allowedPrompts`. |
| Allowed Prompt | `input.allowedPrompts[]` | Values of `input.allowedPrompts[]`. |
| Allowed Prompt Tool | `input.allowedPrompts[].tool` | Values of `input.allowedPrompts[].tool`. |
| Allowed Prompt Prompt | `input.allowedPrompts[].prompt` | Values of `input.allowedPrompts[].prompt`. |
| Skill | `input.skill` | Value of `input.skill`. |
| Plan File Path | `input.planFilePath` | Value of `input.planFilePath`. |
| Plan | `input.plan` | Value of `input.plan`. |
| Questions | `input.questions` | Value of `input.questions`. |
| Question | `input.questions[]` | Values of `input.questions[]`. |
| Question Header | `input.questions[].header` | Values of `input.questions[].header`. |
| Question Question | `input.questions[].question` | Values of `input.questions[].question`. |
| Question Options | `input.questions[].options` | Values of `input.questions[].options`. |
| Question Multi Select | `input.questions[].multiSelect` | Values of `input.questions[].multiSelect`. |
| Todos | `input.todos` | Value of `input.todos`. |
| Todo | `input.todos[]` | Values of `input.todos[]`. |
| Todo Content | `input.todos[].content` | Values of `input.todos[].content`. |
| Todo Status | `input.todos[].status` | Values of `input.todos[].status`. |
| Todo Active Form | `input.todos[].activeForm` | Values of `input.todos[].activeForm`. |
| Active Form | `input.activeForm` | Value of `input.activeForm`. |
| Subject | `input.subject` | Value of `input.subject`. |
| Task ID | `input.task_id` | Value of `input.task_id`. |
| Task ID Variant | `input.taskId` | Value of `input.taskId`. |
| Status | `input.status` | Value of `input.status`. |
| Block | `input.block` | Value of `input.block`. |
| Task | `input.task` | Value of `input.task`. |
| Actions | `input.actions` | Value of `input.actions`. |
| Action | `input.actions[]` | Values of `input.actions[]`. |
| Action Name | `input.actions[].action` | Values of `input.actions[].action`. |
| Action Coordinate | `input.actions[].coordinate` | Values of `input.actions[].coordinate`. |
| Action Duration | `input.actions[].duration` | Values of `input.actions[].duration`. |
| Action Scroll Amount | `input.actions[].scroll_amount` | Values of `input.actions[].scroll_amount`. |
| Action Scroll Direction | `input.actions[].scroll_direction` | Values of `input.actions[].scroll_direction`. |
| Action Start Coordinate | `input.actions[].start_coordinate` | Values of `input.actions[].start_coordinate`. |
| Action Text | `input.actions[].text` | Values of `input.actions[].text`. |
| Coordinate | `input.coordinate` | Value of `input.coordinate`. |
| Coordinate Item | `input.coordinate[]` | Values of `input.coordinate[]`. |
| Start Coordinate | `input.start_coordinate` | Value of `input.start_coordinate`. |
| Start Coordinate Item | `input.start_coordinate[]` | Values of `input.start_coordinate[]`. |
| X | `input.x` | Value of `input.x`. |
| Y | `input.y` | Value of `input.y`. |
| X1 | `input.x1` | Value of `input.x1`. |
| Y1 | `input.y1` | Value of `input.y1`. |
| X2 | `input.x2` | Value of `input.x2`. |
| Y2 | `input.y2` | Value of `input.y2`. |
| Region | `input.region` | Value of `input.region`. |
| Region Item | `input.region[]` | Values of `input.region[]`. |
| Element Index | `input.element_index` | Value of `input.element_index`. |
| Window ID | `input.window_id` | Value of `input.window_id`. |
| PID | `input.pid` | Value of `input.pid`. |
| Session | `input.session` | Value of `input.session`. |
| Capture Mode | `input.capture_mode` | Value of `input.capture_mode`. |
| Screenshot Out File | `input.screenshot_out_file` | Value of `input.screenshot_out_file`. |
| Debug Image Out | `input.debug_image_out` | Value of `input.debug_image_out`. |
| App | `input.app` | Value of `input.app`. |
| Apps | `input.apps` | Value of `input.apps`. |
| App Item | `input.apps[]` | Values of `input.apps[]`. |
| Bundle ID | `input.bundle_id` | Value of `input.bundle_id`. |
| Record Video | `input.record_video` | Value of `input.record_video`. |
| Output Dir | `input.output_dir` | Value of `input.output_dir`. |
| Resource Types | `input.resourceTypes` | Value of `input.resourceTypes`. |
| Resource Type | `input.resourceTypes[]` | Values of `input.resourceTypes[]`. |
| UID | `input.uid` | Value of `input.uid`. |
| Include Snapshot | `input.includeSnapshot` | Value of `input.includeSnapshot`. |
| Text | `input.text` | Value of `input.text`. |
| Key | `input.key` | Value of `input.key`. |
| Action Argument | `input.action` | Value of `input.action`. |
| Type | `input.type` | Value of `input.type`. |
| Types | `input.types` | Value of `input.types`. |
| Type Item | `input.types[]` | Values of `input.types[]`. |
| Title | `input.title` | Value of `input.title`. |
| Name | `input.name` | Value of `input.name`. |
| Value | `input.value` | Value of `input.value`. |
| Summary | `input.summary` | Value of `input.summary`. |
| Reason | `input.reason` | Value of `input.reason`. |
| Question | `input.question` | Value of `input.question`. |
| Pages | `input.pages` | Value of `input.pages`. |
| Duration | `input.duration` | Value of `input.duration`. |
| Interval | `input.interval` | Value of `input.interval`. |
| Until | `input.until` | Value of `input.until`. |
| Persistent | `input.persistent` | Value of `input.persistent`. |
| On Screen Only | `input.on_screen_only` | Value of `input.on_screen_only`. |
| Dangerously Disable Sandbox | `input.dangerouslyDisableSandbox` | Value of `input.dangerouslyDisableSandbox`. |
| System Key Combos | `input.systemKeyCombos` | Value of `input.systemKeyCombos`. |
| Clipboard Read | `input.clipboardRead` | Value of `input.clipboardRead`. |
| Clipboard Write | `input.clipboardWrite` | Value of `input.clipboardWrite`. |
| Save To Disk | `input.save_to_disk` | Value of `input.save_to_disk`. |
| Script | `input.script` | Value of `input.script`. |
| Script Path | `input.scriptPath` | Value of `input.scriptPath`. |
| Scroll Amount | `input.scroll_amount` | Value of `input.scroll_amount`. |
| Scroll Direction | `input.scroll_direction` | Value of `input.scroll_direction`. |
| Delay Seconds | `input.delaySeconds` | Value of `input.delaySeconds`. |
| Max Results | `input.max_results` | Value of `input.max_results`. |
| Allowed Domains | `input.allowed_domains` | Value of `input.allowed_domains`. |
| Allowed Domain | `input.allowed_domains[]` | Values of `input.allowed_domains[]`. |
| Results | `input.results` | Value of `input.results`. |
| Result | `input.results[]` | Values of `input.results[]`. |
| Result Title | `input.results[].title` | Values of `input.results[].title`. |
| Result URL | `input.results[].url` | Values of `input.results[].url`. |
| Result Snippet | `input.results[].snippet` | Values of `input.results[].snippet`. |
| Result Relevance | `input.results[].relevance` | Values of `input.results[].relevance`. |
| Claims | `input.claims` | Value of `input.claims`. |
| Claim | `input.claims[]` | Values of `input.claims[]`. |
| Claim Text | `input.claims[].claim` | Values of `input.claims[].claim`. |
| Claim Importance | `input.claims[].importance` | Values of `input.claims[].importance`. |
| Claim Quote | `input.claims[].quote` | Values of `input.claims[].quote`. |
| Evidence | `input.evidence` | Value of `input.evidence`. |
| Confidence | `input.confidence` | Value of `input.confidence`. |
| Refuted | `input.refuted` | Value of `input.refuted`. |
| Source Quality | `input.sourceQuality` | Value of `input.sourceQuality`. |
| Publish Date | `input.publishDate` | Value of `input.publishDate`. |
| Counter Source | `input.counterSource` | Value of `input.counterSource`. |
| Caveats | `input.caveats` | Value of `input.caveats`. |
| Findings | `input.findings` | Value of `input.findings`. |
| Finding | `input.findings[]` | Values of `input.findings[]`. |
| Finding Claim | `input.findings[].claim` | Values of `input.findings[].claim`. |
| Finding Evidence | `input.findings[].evidence` | Values of `input.findings[].evidence`. |
| Finding Confidence | `input.findings[].confidence` | Values of `input.findings[].confidence`. |
| Finding Sources | `input.findings[].sources` | Values of `input.findings[].sources`. |
| Finding Vote | `input.findings[].vote` | Values of `input.findings[].vote`. |
| Search Angles | `input.angles` | Value of `input.angles`. |
| Search Angle | `input.angles[]` | Values of `input.angles[]`. |
| Search Angle Label | `input.angles[].label` | Values of `input.angles[].label`. |
| Search Angle Query | `input.angles[].query` | Values of `input.angles[].query`. |
| Search Angle Rationale | `input.angles[].rationale` | Values of `input.angles[].rationale`. |
| Issues | `input.issues` | Value of `input.issues`. |
| Issue | `input.issues[]` | Values of `input.issues[]`. |
| Issue Detail | `input.issues[].detail` | Values of `input.issues[].detail`. |
| Issue Kind | `input.issues[].kind` | Values of `input.issues[].kind`. |
| Issue Module | `input.issues[].module` | Values of `input.issues[].module`. |
| Issue Suggestion | `input.issues[].suggestion` | Values of `input.issues[].suggestion`. |
| Open Questions | `input.openQuestions` | Value of `input.openQuestions`. |
| Open Question | `input.openQuestions[]` | Values of `input.openQuestions[]`. |

## Message Navigation Item Design
```text
+--------------------------------------------------------------------------------+
| o  Assistant / Tool Call                                             14:32:07  |
|    Bash: npm test -- --runInBand                                                |
+--------------------------------------------------------------------------------+
  line 1: activity dot, category / subtype, flexible spacer, timestamp
  line 2: summary contents from `name` plus the first populated key input
  tone: assistant-blue; use the same full badge style when badges replace text

Summary contents:
- Start with `name`.
- Append the first available value from `input.command`, `input.file_path`, `input.query`,
  `input.url`, `input.prompt`, `input.description`, `input.content`, `input.args`, or
  the first row label from a key array.
- Middle-truncate long commands, paths, prompts, and content on one navigation line.
- Fall back to `id` only when no key input field is populated.
```

## Message Card Design
```text
Assistant-blue waterfall message card

Title bar
+------------------------------------------------------------------------------------------------+
| o  [Assistant] [Tool Call]  14:32:07  agent/path       [Open Subagent] [Jump] [Raw] [Copy JSON] |
+------------------------------------------------------------------------------------------------+

Content form
+------------------------------------------------------------------------------------------------+
| Tool Call                                                                                      |
| +----------------+---------------------------------------------------------------------------+ |
| | Tool Name      | Bash                                                                      | |
| | Tool Call ID   | toolu_01Wve5tCfHujvEp8s7NUcz1s                                         | |
| | Caller Type    | direct                                                                    | |
| +----------------+---------------------------------------------------------------------------+ |
|                                                                                                |
| Input                                                                                          |
| +----------------+---------------------------------------------------------------------------+ |
| | Description    | Look up both repos with gh                                                | |
| | Command        | gh repo view readycheck-dev/readycheck --json nameWithOwner,...           | |
| | File Path      | /Users/wezzard/.mcp.json                                                  | |
| | Query          | AMOS Atomic macOS Stealer platform targets                                | |
| | URL            | https://code.claude.com/docs/en/claude_code_docs_map.md                   | |
| | Prompt         | MCP server configuration, global settings, bundled servers...              | |
| | Content        | wrapped preview, with expand control for long text                         | |
| +----------------+---------------------------------------------------------------------------+ |
|                                                                                                |
| Actions (array fields use nested tables)                                                       |
| +----+----------------+----------------+----------------+----------------+------------------+ |
| | #  | Action         | Coordinate     | Start Coord.    | Duration       | Text             | |
| +----+----------------+----------------+----------------+----------------+------------------+ |
| | 1  | click          | [688, 480]     |                |                |                  | |
| | 2  | type           |                |                | 1.5            | Say hello        | |
| +----+----------------+----------------+----------------+----------------+------------------+ |
|                                                                                                |
| Allowed Prompts                                                                                |
| +----+------------+------------------------------------------------------------------------+ |
| | #  | Tool       | Prompt                                                                 | |
| +----+------------+------------------------------------------------------------------------+ |
| | 1  | Bash       | initialize the project with pnpm and git                               | |
| +----+------------+------------------------------------------------------------------------+ |
|                                                                                                |
| Questions                                                                                      |
| +----+------------+------------------------------------------+----------------+--------------+ |
| | #  | Header     | Question                                 | Options        | Multi Select | |
| +----+------------+------------------------------------------+----------------+--------------+ |
| | 1  | Terminal   | Which terminal emulator are you running? | 4 options      | false        | |
| +----+------------+------------------------------------------+----------------+--------------+ |
|                                                                                                |
| Todos                                                                                          |
| +----+-------------+------------------------------------------+------------------------------+ |
| | #  | Status      | Content                                  | Active Form                  | |
| +----+-------------+------------------------------------------+------------------------------+ |
| | 1  | in_progress | Rewrite brainstorming/SKILL.md body      | Rewriting brainstorming...    | |
| +----+-------------+------------------------------------------+------------------------------+ |
|                                                                                                |
| Modules                                                                                        |
| +----+----------+---------------------------+---------------------------------------------+ |
| | #  | Module ID | New Module Name           | Module Summary                              | |
| +----+----------+---------------------------+---------------------------------------------+ |
| | 1  | kQr      | otlp-export-delegate      | OpenTelemetry OTLP export delegate...       | |
| +----+----------+---------------------------+---------------------------------------------+ |
| | Rewritten source and rename arrays open in an inline expandable detail panel per module.      | |
| +--------------------------------------------------------------------------------------------+ |
|                                                                                                |
| Results / Claims / Findings                                                                   |
| +----+----------------------+----------------------+-------------------------------------------+ |
| | #  | Title or Claim       | URL or Confidence    | Snippet, Evidence, Quote, or Vote          | |
| +----+----------------------+----------------------+-------------------------------------------+ |
| | 1  | ScreenSpot-Pro...    | https://...          | Dedicated dated leaderboard...             | |
| +----+----------------------+----------------------+-------------------------------------------+ |
|                                                                                                |
| Raw and Fallback                                                                               |
| +----------------------+---------------------------------------------------------------------+ |
| | Parsed JSON mirrors   | Hide `input.*.$json` by default; expose in Raw.                    | |
| | Unparsed tool input   | Show compact warning row; Raw contains `input.__unparsedToolInput`. | |
| +----------------------+---------------------------------------------------------------------+ |
+------------------------------------------------------------------------------------------------+

Open Subagent and Jump to First appear only for Agent/Task-style calls that have enough target
context. Raw opens formatted raw JSON for this timeline item; Copy JSON copies the raw payload.
```
