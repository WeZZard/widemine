# Detail Popup Content Design - Assistant / Tool Call

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Caller | `caller` | Records caller mode for transcript context; keep outside Content rows. | Observed types: object. Observed count: 42448. | false |
| Type | `caller.type` | Records caller mode for transcript context; keep outside Content rows. | Observed types: string. Observed count: 42448. | false |
| ID | `id` | Identifies the tool request for matching with tool results. | Observed types: string. Observed count: 42448. | true |
| Input | `input` | Container for tool input arguments; flattened child paths define Content rows. | Observed types: object. Observed count: 42448. | false |
| Function Name | `input.$FUNCTION_NAME` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 2. | false |
| Unparsed Tool Input | `input.__unparsedToolInput` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 4. | false |
| Len | `input.__unparsedToolInput.len` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: number. Observed count: 4. | false |
| Raw | `input.__unparsedToolInput.raw` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 4. | false |
| Action | `input.action` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 4. | true |
| Actions | `input.actions` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 12. | false |
| Actions Items | `input.actions[]` | Container for flattened child fields; child rows carry Content rendering. | Observed types: object. Observed count: 34. | false |
| Action | `input.actions[].action` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 34. | true |
| Coordinate | `input.actions[].coordinate` | Captures a concrete tool input argument for the request. | Observed types: array. Observed count: 11. | true |
| Duration | `input.actions[].duration` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 6. | true |
| Scroll Amount | `input.actions[].scroll_amount` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 1. | true |
| Scroll Direction | `input.actions[].scroll_direction` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1. | true |
| Start Coordinate | `input.actions[].start_coordinate` | Captures a concrete tool input argument for the request. | Observed types: array. Observed count: 1. | true |
| Text | `input.actions[].text` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 5. | true |
| Active Form | `input.activeForm` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 19. | true |
| Allowed Prompts | `input.allowedPrompts` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 224. | false |
| Allowed Prompts Items | `input.allowedPrompts[]` | Container for flattened child fields; child rows carry Content rendering. | Observed types: object. Observed count: 662. | false |
| Prompt | `input.allowedPrompts[].prompt` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 662. | true |
| Tool | `input.allowedPrompts[].tool` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 662. | true |
| Allowed Domains | `input.allowed_domains` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 47. | false |
| Allowed Domains Items | `input.allowed_domains[]` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 91. | true |
| Angles | `input.angles` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 1. | false |
| Angles Items | `input.angles[]` | Container for flattened child fields; child rows carry Content rendering. | Observed types: object. Observed count: 5. | false |
| Label | `input.angles[].label` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 5. | true |
| Query | `input.angles[].query` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 5. | true |
| Rationale | `input.angles[].rationale` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 5. | true |
| App | `input.app` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 10. | true |
| Apps | `input.apps` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 73. | false |
| Apps Items | `input.apps[]` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 93. | true |
| Args | `input.args` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 167. | true |
| JSON | `input.args.$json` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 31. | false |
| Batches | `input.args.$json.batches` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: number. Observed count: 7. | false |
| Cluster Name | `input.args.$json.clusterName` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 2. | false |
| Done Substantive | `input.args.$json.doneSubstantive` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: number. Observed count: 1. | false |
| Gbytes | `input.args.$json.gbytes` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: number. Observed count: 8. | false |
| Gcount | `input.args.$json.gcount` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: number. Observed count: 8. | false |
| Groups | `input.args.$json.groups` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: array. Observed count: 13. | false |
| Levels | `input.args.$json.levels` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 2. | false |
| Max Bytes | `input.args.$json.maxBytes` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: number. Observed count: 7. | false |
| Max M | `input.args.$json.maxM` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: number. Observed count: 8. | false |
| Modules | `input.args.$json.modules` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: array, object. Observed count: 3. | false |
| Node Path | `input.args.$json.nodePath` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 8. | false |
| Order | `input.args.$json.order` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: array. Observed count: 2. | false |
| Remaining Substantive | `input.args.$json.remainingSubstantive` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: number. Observed count: 1. | false |
| Repo Abs | `input.args.$json.repoAbs` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 24. | false |
| Total Substantive | `input.args.$json.totalSubstantive` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: number. Observed count: 1. | false |
| Total Trivial | `input.args.$json.totalTrivial` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: number. Observed count: 1. | false |
| Wave Dir | `input.args.$json.waveDir` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 7. | false |
| Batch | `input.batch` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 827. | true |
| Block | `input.block` | Captures a concrete tool input argument for the request. | Observed types: bool. Observed count: 14. | true |
| Bundle ID | `input.bundle_id` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 6. | true |
| Capture Mode | `input.capture_mode` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 30. | true |
| Caveats | `input.caveats` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1. | true |
| Claims | `input.claims` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 20. | false |
| Claims Items | `input.claims[]` | Container for flattened child fields; child rows carry Content rendering. | Observed types: object. Observed count: 85. | false |
| Claim | `input.claims[].claim` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 85. | true |
| Importance | `input.claims[].importance` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 85. | true |
| Quote | `input.claims[].quote` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 85. | true |
| Clipboard Read | `input.clipboardRead` | Captures a concrete tool input argument for the request. | Observed types: bool. Observed count: 1. | true |
| Clipboard Write | `input.clipboardWrite` | Captures a concrete tool input argument for the request. | Observed types: bool. Observed count: 1. | true |
| Command | `input.command` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 21449. | true |
| Confidence | `input.confidence` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 75. | true |
| Content | `input.content` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1579. | true |
| JSON | `input.content.$json` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: array, object. Observed count: 935. | false |
| Defs | `input.content.$json.$defs` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 1. | false |
| ID | `input.content.$json.$id` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 1. | false |
| Schema | `input.content.$json.$schema` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 3. | false |
| Note | `input.content.$json._note` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 1. | false |
| Additional Properties | `input.content.$json.additionalProperties` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: bool. Observed count: 1. | false |
| Author | `input.content.$json.author` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 1. | false |
| Capabilities | `input.content.$json.capabilities` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: array. Observed count: 2. | false |
| Compiler Options | `input.content.$json.compilerOptions` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 1. | false |
| Dependencies | `input.content.$json.dependencies` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 2. | false |
| Description | `input.content.$json.description` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 3. | false |
| Dev Dependencies | `input.content.$json.devDependencies` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 1. | false |
| Engines | `input.content.$json.engines` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 1. | false |
| Function | `input.content.$json.function` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 7. | false |
| Homepage | `input.content.$json.homepage` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 1. | false |
| Include | `input.content.$json.include` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: array. Observed count: 1. | false |
| Inputs | `input.content.$json.inputs` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: array. Observed count: 1. | false |
| Interface | `input.content.$json.interface` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 1. | false |
| Keywords | `input.content.$json.keywords` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: array. Observed count: 1. | false |
| License | `input.content.$json.license` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 1. | false |
| Name | `input.content.$json.name` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 5. | false |
| Nodes | `input.content.$json.nodes` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: array. Observed count: 55. | false |
| Outputs | `input.content.$json.outputs` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: array. Observed count: 1. | false |
| Plan File | `input.content.$json.plan_file` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 25. | false |
| Private | `input.content.$json.private` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: bool. Observed count: 1. | false |
| Properties | `input.content.$json.properties` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 1. | false |
| Provider | `input.content.$json.provider` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 1. | false |
| Providers | `input.content.$json.providers` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 1. | false |
| Renames | `input.content.$json.renames` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: array. Observed count: 833. | false |
| Repository | `input.content.$json.repository` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 1. | false |
| Required | `input.content.$json.required` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: array. Observed count: 1. | false |
| Scripts | `input.content.$json.scripts` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 1. | false |
| Skills | `input.content.$json.skills` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 1. | false |
| Title | `input.content.$json.title` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 1. | false |
| Type | `input.content.$json.type` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 10. | false |
| Variables | `input.content.$json.variables` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 25. | false |
| Version | `input.content.$json.version` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: number, string. Observed count: 56. | false |
| JSON Items | `input.content.$json[]` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 68. | false |
| Coordinate | `input.coordinate` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 22. | false |
| Coordinate Items | `input.coordinate[]` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 44. | true |
| Counter Source | `input.counterSource` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 74. | true |
| Dangerously Disable Sandbox | `input.dangerouslyDisableSandbox` | Captures a concrete tool input argument for the request. | Observed types: bool. Observed count: 31. | true |
| Debug Image Out | `input.debug_image_out` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1. | true |
| Delay Seconds | `input.delaySeconds` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 21. | true |
| Description | `input.description` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 14025. | true |
| Duration | `input.duration` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 10. | true |
| Element Index | `input.element_index` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 13. | true |
| Evidence | `input.evidence` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 75. | true |
| File Path | `input.file_path` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 14600. | true |
| Findings | `input.findings` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 1. | false |
| Findings Items | `input.findings[]` | Container for flattened child fields; child rows carry Content rendering. | Observed types: object. Observed count: 10. | false |
| Claim | `input.findings[].claim` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 10. | true |
| Confidence | `input.findings[].confidence` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 10. | true |
| Evidence | `input.findings[].evidence` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 10. | true |
| Sources | `input.findings[].sources` | Captures a concrete tool input argument for the request. | Observed types: array. Observed count: 10. | true |
| Vote | `input.findings[].vote` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 10. | true |
| Global Renames | `input.globalRenames` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 13. | false |
| Global Renames Items | `input.globalRenames[]` | Container for flattened child fields; child rows carry Content rendering. | Observed types: object. Observed count: 36. | false |
| Doc | `input.globalRenames[].doc` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 36. | true |
| Kind | `input.globalRenames[].kind` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 36. | true |
| New | `input.globalRenames[].new` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 36. | true |
| Old | `input.globalRenames[].old` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 36. | true |
| ID | `input.id` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 18. | true |
| Include Snapshot | `input.includeSnapshot` | Captures a concrete tool input argument for the request. | Observed types: bool. Observed count: 1. | true |
| Interval | `input.interval` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1. | true |
| Issues | `input.issues` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 1. | false |
| Issues Items | `input.issues[]` | Container for flattened child fields; child rows carry Content rendering. | Observed types: object. Observed count: 8. | false |
| Detail | `input.issues[].detail` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 8. | true |
| Kind | `input.issues[].kind` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 8. | true |
| Module | `input.issues[].module` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 8. | true |
| Suggestion | `input.issues[].suggestion` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 8. | true |
| Key | `input.key` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 5. | true |
| Limit | `input.limit` | Captures a concrete tool input argument for the request. | Observed types: number, string. Observed count: 2343. | true |
| Max Results | `input.max_results` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 370. | true |
| Model | `input.model` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 456. | true |
| Module Summary | `input.moduleSummary` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 18. | true |
| Modules | `input.modules` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array, object. Observed count: 648. | false |
| Modules | `input.modules.modules` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 3. | false |
| Modules Items | `input.modules.modules[]` | Captures a concrete tool input argument for the request. | Observed types: object. Observed count: 9. | true |
| Modules Items | `input.modules[]` | Container for flattened child fields; child rows carry Content rendering. | Observed types: object. Observed count: 1687. | false |
| Global Renames | `input.modules[].globalRenames` | Captures a concrete tool input argument for the request. | Observed types: array. Observed count: 1686. | true |
| ID | `input.modules[].id` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1687. | true |
| Known Names | `input.modules[].knownNames` | Captures a concrete tool input argument for the request. | Observed types: object. Observed count: 3. | true |
| Module Summary | `input.modules[].moduleSummary` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1687. | true |
| New Module Name | `input.modules[].newModuleName` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1687. | true |
| Rewritten Source | `input.modules[].rewrittenSource` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1685. | true |
| Name | `input.name` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 3. | true |
| New Module Name | `input.newModuleName` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 18. | true |
| New String | `input.new_string` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 2931. | true |
| Notes | `input.notes` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1. | true |
| Offset | `input.offset` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array, number. Observed count: 1662. | false |
| Offset Items | `input.offset[]` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 58. | true |
| Old String | `input.old_string` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 2931. | true |
| JSON | `input.old_string.$json` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 1. | false |
| Agent | `input.old_string.$json.agent` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 1. | false |
| Deps | `input.old_string.$json.deps` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: array. Observed count: 1. | false |
| ID | `input.old_string.$json.id` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 1. | false |
| Kind | `input.old_string.$json.kind` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 1. | false |
| Prompt Template | `input.old_string.$json.promptTemplate` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: string. Observed count: 1. | false |
| Schema | `input.old_string.$json.schema` | Parser-expanded or internal path; keep in Metadata and Raw. | Observed types: object. Observed count: 1. | false |
| On Screen Only | `input.on_screen_only` | Captures a concrete tool input argument for the request. | Observed types: bool. Observed count: 1. | true |
| Open Questions | `input.openQuestions` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 1. | false |
| Open Questions Items | `input.openQuestions[]` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 4. | true |
| Output Dir | `input.output_dir` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 4. | true |
| Pages | `input.pages` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1. | true |
| Persistent | `input.persistent` | Captures a concrete tool input argument for the request. | Observed types: bool. Observed count: 159. | true |
| PID | `input.pid` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 89. | true |
| Plan | `input.plan` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 247. | true |
| Plan File Path | `input.planFilePath` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 247. | true |
| Prompt | `input.prompt` | Captures a concrete tool input argument for the request. | Observed types: bool, string. Observed count: 2121. | true |
| Publish Date | `input.publishDate` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 20. | true |
| Query | `input.query` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1152. | true |
| Question | `input.question` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1. | true |
| Questions | `input.questions` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 378. | false |
| Questions Items | `input.questions[]` | Container for flattened child fields; child rows carry Content rendering. | Observed types: object. Observed count: 516. | false |
| Header | `input.questions[].header` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 516. | true |
| Multi Select | `input.questions[].multiSelect` | Captures a concrete tool input argument for the request. | Observed types: bool. Observed count: 516. | true |
| Options | `input.questions[].options` | Captures a concrete tool input argument for the request. | Observed types: array. Observed count: 516. | true |
| Question | `input.questions[].question` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 516. | true |
| Reason | `input.reason` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 94. | true |
| Record Video | `input.record_video` | Captures a concrete tool input argument for the request. | Observed types: bool. Observed count: 4. | true |
| Refuted | `input.refuted` | Captures a concrete tool input argument for the request. | Observed types: bool. Observed count: 75. | true |
| Region | `input.region` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 20. | false |
| Region Items | `input.region[]` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 80. | true |
| Replace All | `input.replace_all` | Captures a concrete tool input argument for the request. | Observed types: bool. Observed count: 2931. | true |
| Resource Types | `input.resourceTypes` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 3. | false |
| Resource Types Items | `input.resourceTypes[]` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 11. | true |
| Results | `input.results` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 5. | false |
| Results Items | `input.results[]` | Container for flattened child fields; child rows carry Content rendering. | Observed types: object. Observed count: 30. | false |
| Relevance | `input.results[].relevance` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 30. | true |
| Snippet | `input.results[].snippet` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 30. | true |
| Title | `input.results[].title` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 30. | true |
| URL | `input.results[].url` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 30. | true |
| Rewritten Source | `input.rewrittenSource` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 18. | true |
| Run In Background | `input.run_in_background` | Captures a concrete tool input argument for the request. | Observed types: bool. Observed count: 847. | true |
| Save To Disk | `input.save_to_disk` | Captures a concrete tool input argument for the request. | Observed types: bool. Observed count: 1. | true |
| Screenshot Out File | `input.screenshot_out_file` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 26. | true |
| Script | `input.script` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1. | true |
| Script Path | `input.scriptPath` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 31. | true |
| Scroll Amount | `input.scroll_amount` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 1. | true |
| Scroll Direction | `input.scroll_direction` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1. | true |
| Session | `input.session` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 69. | true |
| Skill | `input.skill` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 295. | true |
| Source Quality | `input.sourceQuality` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 20. | true |
| Start Coordinate | `input.start_coordinate` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 6. | false |
| Start Coordinate Items | `input.start_coordinate[]` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 12. | true |
| Status | `input.status` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 37. | true |
| Subagent Type | `input.subagent_type` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1124. | true |
| Subject | `input.subject` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 19. | true |
| Summary | `input.summary` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 5. | true |
| System Key Combos | `input.systemKeyCombos` | Captures a concrete tool input argument for the request. | Observed types: bool. Observed count: 2. | true |
| Task | `input.task` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1. | true |
| Task ID | `input.taskId` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 37. | true |
| Task ID | `input.task_id` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 52. | true |
| Text | `input.text` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 7. | true |
| Timeout | `input.timeout` | Captures a concrete tool input argument for the request. | Observed types: number, string. Observed count: 1514. | true |
| Timeout Ms | `input.timeout_ms` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 148. | true |
| Title | `input.title` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 3. | true |
| Todos | `input.todos` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 30. | false |
| Todos Items | `input.todos[]` | Container for flattened child fields; child rows carry Content rendering. | Observed types: object. Observed count: 192. | false |
| Active Form | `input.todos[].activeForm` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 192. | true |
| Content | `input.todos[].content` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 192. | true |
| Status | `input.todos[].status` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 192. | true |
| Type | `input.type` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 4. | true |
| Types | `input.types` | Container for flattened child fields; child rows carry Content rendering. | Observed types: array. Observed count: 1. | false |
| Types Items | `input.types[]` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 2. | true |
| UID | `input.uid` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 2. | true |
| Until | `input.until` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 2. | true |
| URL | `input.url` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 922. | true |
| Value | `input.value` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1. | true |
| Verdict | `input.verdict` | Captures a concrete tool input argument for the request. | Observed types: string. Observed count: 1. | true |
| Window ID | `input.window_id` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 76. | true |
| Written | `input.written` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 827. | true |
| X | `input.x` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 10. | true |
| X1 | `input.x1` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 18. | true |
| X2 | `input.x2` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 18. | true |
| Y | `input.y` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 10. | true |
| Y1 | `input.y1` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 18. | true |
| Y2 | `input.y2` | Captures a concrete tool input argument for the request. | Observed types: number. Observed count: 18. | true |
| Name | `name` | Names the requested tool. | Observed types: string. Observed count: 42448. | true |
| Type | `type` | Routes the transcript item; the titlebar owns category display. | Observed types: string. Observed count: 42448. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| ID | `id` | Read from `id` when present; otherwise show `Not provided`. | Render as a compact copyable identifier. |
| Action | `input.action` | Read from `input.action` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Action | `input.actions[].action` | Read from `input.actions[].action` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Coordinate | `input.actions[].coordinate` | Read from `input.actions[].coordinate` when present; otherwise show `Not provided`. | Render structured values as nested rows; place long content in bounded scroll cells with preserved line breaks. |
| Duration | `input.actions[].duration` | Read from `input.actions[].duration` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Scroll Amount | `input.actions[].scroll_amount` | Read from `input.actions[].scroll_amount` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Scroll Direction | `input.actions[].scroll_direction` | Read from `input.actions[].scroll_direction` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Start Coordinate | `input.actions[].start_coordinate` | Read from `input.actions[].start_coordinate` when present; otherwise show `Not provided`. | Render structured values as nested rows; place long content in bounded scroll cells with preserved line breaks. |
| Text | `input.actions[].text` | Read from `input.actions[].text` when present; otherwise show `Not provided`. | Render as complete wrapped multiline text in a bounded scroll area with preserved line breaks. |
| Active Form | `input.activeForm` | Read from `input.activeForm` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Prompt | `input.allowedPrompts[].prompt` | Read from `input.allowedPrompts[].prompt` when present; otherwise show `Not provided`. | Render as complete wrapped multiline text in a bounded scroll area with preserved line breaks. |
| Tool | `input.allowedPrompts[].tool` | Read from `input.allowedPrompts[].tool` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Allowed Domains Items | `input.allowed_domains[]` | Read from `input.allowed_domains[]` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Label | `input.angles[].label` | Read from `input.angles[].label` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Query | `input.angles[].query` | Read from `input.angles[].query` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Rationale | `input.angles[].rationale` | Read from `input.angles[].rationale` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| App | `input.app` | Read from `input.app` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Apps Items | `input.apps[]` | Read from `input.apps[]` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Args | `input.args` | Read from `input.args` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Batch | `input.batch` | Read from `input.batch` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Block | `input.block` | Read from `input.block` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Bundle ID | `input.bundle_id` | Read from `input.bundle_id` when present; otherwise show `Not provided`. | Render as a compact copyable identifier. |
| Capture Mode | `input.capture_mode` | Read from `input.capture_mode` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Caveats | `input.caveats` | Read from `input.caveats` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Claim | `input.claims[].claim` | Read from `input.claims[].claim` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Importance | `input.claims[].importance` | Read from `input.claims[].importance` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Quote | `input.claims[].quote` | Read from `input.claims[].quote` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Clipboard Read | `input.clipboardRead` | Read from `input.clipboardRead` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Clipboard Write | `input.clipboardWrite` | Read from `input.clipboardWrite` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Command | `input.command` | Read from `input.command` when present; otherwise show `Not provided`. | Render multiline values in a monospace block with copy affordance. |
| Confidence | `input.confidence` | Read from `input.confidence` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Content | `input.content` | Read from `input.content` when present; otherwise show `Not provided`. | Render as complete wrapped multiline text in a bounded scroll area with preserved line breaks. |
| Coordinate Items | `input.coordinate[]` | Read from `input.coordinate[]` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Counter Source | `input.counterSource` | Read from `input.counterSource` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Dangerously Disable Sandbox | `input.dangerouslyDisableSandbox` | Read from `input.dangerouslyDisableSandbox` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Debug Image Out | `input.debug_image_out` | Read from `input.debug_image_out` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Delay Seconds | `input.delaySeconds` | Read from `input.delaySeconds` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Description | `input.description` | Read from `input.description` when present; otherwise show `Not provided`. | Render as complete wrapped multiline text in a bounded scroll area with preserved line breaks. |
| Duration | `input.duration` | Read from `input.duration` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Element Index | `input.element_index` | Read from `input.element_index` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Evidence | `input.evidence` | Read from `input.evidence` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| File Path | `input.file_path` | Read from `input.file_path` when present; otherwise show `Not provided`. | Render as a copyable path or URL row, truncating the middle when long. |
| Claim | `input.findings[].claim` | Read from `input.findings[].claim` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Confidence | `input.findings[].confidence` | Read from `input.findings[].confidence` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Evidence | `input.findings[].evidence` | Read from `input.findings[].evidence` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Sources | `input.findings[].sources` | Read from `input.findings[].sources` when present; otherwise show `Not provided`. | Render structured values as nested rows; place long content in bounded scroll cells with preserved line breaks. |
| Vote | `input.findings[].vote` | Read from `input.findings[].vote` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Doc | `input.globalRenames[].doc` | Read from `input.globalRenames[].doc` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Kind | `input.globalRenames[].kind` | Read from `input.globalRenames[].kind` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| New | `input.globalRenames[].new` | Read from `input.globalRenames[].new` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Old | `input.globalRenames[].old` | Read from `input.globalRenames[].old` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| ID | `input.id` | Read from `input.id` when present; otherwise show `Not provided`. | Render as a compact copyable identifier. |
| Include Snapshot | `input.includeSnapshot` | Read from `input.includeSnapshot` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Interval | `input.interval` | Read from `input.interval` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Detail | `input.issues[].detail` | Read from `input.issues[].detail` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Kind | `input.issues[].kind` | Read from `input.issues[].kind` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Module | `input.issues[].module` | Read from `input.issues[].module` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Suggestion | `input.issues[].suggestion` | Read from `input.issues[].suggestion` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Key | `input.key` | Read from `input.key` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Limit | `input.limit` | Read from `input.limit` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Max Results | `input.max_results` | Read from `input.max_results` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Model | `input.model` | Read from `input.model` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Module Summary | `input.moduleSummary` | Read from `input.moduleSummary` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Modules Items | `input.modules.modules[]` | Read from `input.modules.modules[]` when present; otherwise show `Not provided`. | Render structured values as nested rows; place long content in bounded scroll cells with preserved line breaks. |
| Global Renames | `input.modules[].globalRenames` | Read from `input.modules[].globalRenames` when present; otherwise show `Not provided`. | Render structured values as nested rows; place long content in bounded scroll cells with preserved line breaks. |
| ID | `input.modules[].id` | Read from `input.modules[].id` when present; otherwise show `Not provided`. | Render as a compact copyable identifier. |
| Known Names | `input.modules[].knownNames` | Read from `input.modules[].knownNames` when present; otherwise show `Not provided`. | Render structured values as nested rows; place long content in bounded scroll cells with preserved line breaks. |
| Module Summary | `input.modules[].moduleSummary` | Read from `input.modules[].moduleSummary` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| New Module Name | `input.modules[].newModuleName` | Read from `input.modules[].newModuleName` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Rewritten Source | `input.modules[].rewrittenSource` | Read from `input.modules[].rewrittenSource` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Name | `input.name` | Read from `input.name` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| New Module Name | `input.newModuleName` | Read from `input.newModuleName` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| New String | `input.new_string` | Read from `input.new_string` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Notes | `input.notes` | Read from `input.notes` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Offset Items | `input.offset[]` | Read from `input.offset[]` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Old String | `input.old_string` | Read from `input.old_string` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| On Screen Only | `input.on_screen_only` | Read from `input.on_screen_only` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Open Questions Items | `input.openQuestions[]` | Read from `input.openQuestions[]` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Output Dir | `input.output_dir` | Read from `input.output_dir` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Pages | `input.pages` | Read from `input.pages` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Persistent | `input.persistent` | Read from `input.persistent` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| PID | `input.pid` | Read from `input.pid` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Plan | `input.plan` | Read from `input.plan` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Plan File Path | `input.planFilePath` | Read from `input.planFilePath` when present; otherwise show `Not provided`. | Render as a copyable path or URL row, truncating the middle when long. |
| Prompt | `input.prompt` | Read from `input.prompt` when present; otherwise show `Not provided`. | Render as complete wrapped multiline text in a bounded scroll area with preserved line breaks. |
| Publish Date | `input.publishDate` | Read from `input.publishDate` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Query | `input.query` | Read from `input.query` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Question | `input.question` | Read from `input.question` when present; otherwise show `Not provided`. | Render as complete wrapped multiline text in a bounded scroll area with preserved line breaks. |
| Header | `input.questions[].header` | Read from `input.questions[].header` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Multi Select | `input.questions[].multiSelect` | Read from `input.questions[].multiSelect` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Options | `input.questions[].options` | Read from `input.questions[].options` when present; otherwise show `Not provided`. | Render structured values as nested rows; place long content in bounded scroll cells with preserved line breaks. |
| Question | `input.questions[].question` | Read from `input.questions[].question` when present; otherwise show `Not provided`. | Render as complete wrapped multiline text in a bounded scroll area with preserved line breaks. |
| Reason | `input.reason` | Read from `input.reason` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Record Video | `input.record_video` | Read from `input.record_video` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Refuted | `input.refuted` | Read from `input.refuted` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Region Items | `input.region[]` | Read from `input.region[]` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Replace All | `input.replace_all` | Read from `input.replace_all` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Resource Types Items | `input.resourceTypes[]` | Read from `input.resourceTypes[]` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Relevance | `input.results[].relevance` | Read from `input.results[].relevance` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Snippet | `input.results[].snippet` | Read from `input.results[].snippet` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Title | `input.results[].title` | Read from `input.results[].title` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| URL | `input.results[].url` | Read from `input.results[].url` when present; otherwise show `Not provided`. | Render as a copyable path or URL row, truncating the middle when long. |
| Rewritten Source | `input.rewrittenSource` | Read from `input.rewrittenSource` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Run In Background | `input.run_in_background` | Read from `input.run_in_background` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Save To Disk | `input.save_to_disk` | Read from `input.save_to_disk` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Screenshot Out File | `input.screenshot_out_file` | Read from `input.screenshot_out_file` when present; otherwise show `Not provided`. | Render as a copyable path or URL row, truncating the middle when long. |
| Script | `input.script` | Read from `input.script` when present; otherwise show `Not provided`. | Render multiline values in a monospace block with copy affordance. |
| Script Path | `input.scriptPath` | Read from `input.scriptPath` when present; otherwise show `Not provided`. | Render as a copyable path or URL row, truncating the middle when long. |
| Scroll Amount | `input.scroll_amount` | Read from `input.scroll_amount` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Scroll Direction | `input.scroll_direction` | Read from `input.scroll_direction` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Session | `input.session` | Read from `input.session` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Skill | `input.skill` | Read from `input.skill` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Source Quality | `input.sourceQuality` | Read from `input.sourceQuality` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Start Coordinate Items | `input.start_coordinate[]` | Read from `input.start_coordinate[]` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Status | `input.status` | Read from `input.status` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Subagent Type | `input.subagent_type` | Read from `input.subagent_type` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Subject | `input.subject` | Read from `input.subject` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Summary | `input.summary` | Read from `input.summary` when present; otherwise show `Not provided`. | Render as complete wrapped multiline text in a bounded scroll area with preserved line breaks. |
| System Key Combos | `input.systemKeyCombos` | Read from `input.systemKeyCombos` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Task | `input.task` | Read from `input.task` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Task ID | `input.taskId` | Read from `input.taskId` when present; otherwise show `Not provided`. | Render as a compact copyable identifier. |
| Task ID | `input.task_id` | Read from `input.task_id` when present; otherwise show `Not provided`. | Render as a compact copyable identifier. |
| Text | `input.text` | Read from `input.text` when present; otherwise show `Not provided`. | Render as complete wrapped multiline text in a bounded scroll area with preserved line breaks. |
| Timeout | `input.timeout` | Read from `input.timeout` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Timeout Ms | `input.timeout_ms` | Read from `input.timeout_ms` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Title | `input.title` | Read from `input.title` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Active Form | `input.todos[].activeForm` | Read from `input.todos[].activeForm` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Content | `input.todos[].content` | Read from `input.todos[].content` when present; otherwise show `Not provided`. | Render as complete wrapped multiline text in a bounded scroll area with preserved line breaks. |
| Status | `input.todos[].status` | Read from `input.todos[].status` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Type | `input.type` | Read from `input.type` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Types Items | `input.types[]` | Read from `input.types[]` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| UID | `input.uid` | Read from `input.uid` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Until | `input.until` | Read from `input.until` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| URL | `input.url` | Read from `input.url` when present; otherwise show `Not provided`. | Render as a copyable path or URL row, truncating the middle when long. |
| Value | `input.value` | Read from `input.value` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Verdict | `input.verdict` | Read from `input.verdict` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Window ID | `input.window_id` | Read from `input.window_id` when present; otherwise show `Not provided`. | Render as a compact copyable identifier. |
| Written | `input.written` | Read from `input.written` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| X | `input.x` | Read from `input.x` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| X1 | `input.x1` | Read from `input.x1` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| X2 | `input.x2` | Read from `input.x2` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Y | `input.y` | Read from `input.y` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Y1 | `input.y1` | Read from `input.y1` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Y2 | `input.y2` | Read from `input.y2` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |
| Name | `name` | Read from `name` when present; otherwise show `Not provided`. | Render as a labeled form row using the value native scalar formatting. |

## Card Design

```text
+------------------------------------------------------------------------------------------------+
| [Assistant] [Tool Call]                                                            [pin] [x] |
+------------------------------------------------------------------------------------------------+
|                                  Content | Metadata | Raw                                    |
+------------------------------------------------------------------------------------------------+
| ID                  <value from id>                                                        |
| Name                <value from name>                                                      |
| Action              <value from input.action>                                              |
| Command             <value from input.command>                                             |
| File Path           <value from input.file_path>                                           |
| Content             <value from input.content>                                             |
| Args                <value from input.args>                                                |
| Prompt              <value from input.prompt>                                              |
| Query               <value from input.query>                                               |
| Status              <value from input.status>                                              |
| Timeout             <value from input.timeout>                                             |
| URL                 <value from input.url>                                                 |
| ...                 <remaining non-array key fields in source order>                       |
|                                                                                                |
| Actions                                                                                       |
|  | Action | Coordinate | Duration | Scroll Amount | Scroll Direction | Start Coordinate | Text |
|   | <input.actions[].action> | <input.actions[].coordinate> | <input.actions[].duration> | ... |
| Allowed Prompts                                                                               |
|   | Prompt | Tool                                                                          |
|   | <input.allowedPrompts[].prompt> | <input.allowedPrompts[].tool>                         |
| Allowed Domains                                                                               |
|   | Allowed Domains Items                                                                  |
|   | <input.allowed_domains[]>                                                              |
| Angles                                                                                         |
|   | Label | Query | Rationale                                                              |
|   | <input.angles[].label> | <input.angles[].query> | <input.angles[].rationale>           |
| Apps                                                                                           |
|   | Apps Items                                                                              |
|   | <input.apps[]>                                                                         |
| Claims                                                                                         |
|   | Claim | Importance | Quote                                                             |
|   | <input.claims[].claim> | <input.claims[].importance> | <input.claims[].quote>          |
| Coordinate                                                                                     |
|   | Coordinate Items                                                                        |
|   | <input.coordinate[]>                                                                    |
| Findings                                                                                       |
|   | Claim | Confidence | Evidence | Sources | Vote                                         |
|   | <input.findings[].claim> | <...> | <...> | <...> | <...>                          |
| Global Renames                                                                                 |
|   | Doc | Kind | New | Old                                                                 |
|   | <input.globalRenames[].doc> | <...> | <...> | <...>                            |
| Issues                                                                                         |
|   | Detail | Kind | Module | Suggestion                                                    |
|   | <input.issues[].detail> | <input.issues[].kind> | <input.issues[].module> | ...       |
| Modules                                                                                        |
|   | ID | Module Summary | New Module Name | Rewritten Source | Known Names | Global Renames |
|   | <input.modules[].id> | <...> | <...> | <...> | <...> | <...>                      |
| Modules Modules                                                                                |
|   | Modules Items                                                                           |
|   | <input.modules.modules[]>                                                               |
| Offset                                                                                         |
|   | Offset Items                                                                            |
|   | <input.offset[]>                                                                        |
| Open Questions                                                                                 |
|   | Open Questions Items                                                                    |
|   | <input.openQuestions[]>                                                                 |
| Questions                                                                                      |
|   | Header | Multi Select | Options | Question                                             |
|   | <input.questions[].header> | <...> | <...> | <...>                            |
| Region                                                                                         |
|   | Region Items                                                                            |
|   | <input.region[]>                                                                        |
| Resource Types                                                                                 |
|   | Resource Types Items                                                                    |
|   | <input.resourceTypes[]>                                                                 |
| Results                                                                                        |
|   | Relevance | Snippet | Title | URL                                                      |
|   | <input.results[].relevance> | <input.results[].snippet> | <input.results[].title> | ...   |
| Start Coordinate                                                                               |
|   | Start Coordinate Items                                                                  |
|   | <input.start_coordinate[]>                                                              |
| Todos                                                                                          |
|   | Active Form | Content | Status                                                         |
|   | <input.todos[].activeForm> | <input.todos[].content> | <input.todos[].status>           |
| Types                                                                                          |
|   | Types Items                                                                             |
|   | <input.types[]>                                                                         |
+------------------------------------------------------------------------------------------------+
```
