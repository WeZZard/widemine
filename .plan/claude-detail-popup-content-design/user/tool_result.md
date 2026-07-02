# Detail Popup Content Design - User / Tool Result

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Is Error | `is_error` | Shows whether the tool result is an error outcome. | Observed types: bool. Shapes: 55. Count: 21852. | true |
| Tool Use ID | `tool_use_id` | Pairs this result with the tool call that produced it. | Observed types: string. Shapes: 75. Count: 42411. Max length: 30. | true |
| Content | `content` | Primary tool result payload, either direct text or typed content blocks. | Observed types: array, string. Shapes: 75. Count: 42411. Max length: 87555. Max items: 24. | true |
| Content Items | `content[]` | Array container for typed result blocks; child fields define the visible block content. | Observed types: object. Shapes: 6. Count: 2597. | false |
| Text | `content[].text` | Text body inside a typed result block. | Observed types: string. Shapes: 4. Count: 1817. Max length: 48645. | true |
| Tool Name | `content[].tool_name` | Tool name attached to a typed result block when the payload includes it. | Observed types: string. Shapes: 1. Count: 682. Max length: 68. | true |
| Source | `content[].source` | Embedded source container for rich result content; child fields define rendering. | Observed types: object. Shapes: 3. Count: 98. | false |
| Media Type | `content[].source.media_type` | Media type for embedded rich result content. | Observed types: string. Shapes: 3. Count: 98. Max length: 10. | true |
| Data | `content[].source.data` | Embedded rich result data, such as encoded image content. | Observed types: string. Shapes: 3. Count: 98. Max length: 551108. | true |
| Type | `content[].source.type` | Embedded source encoding discriminator used by the renderer. | Observed types: string. Shapes: 3. Count: 98. Max length: 6. | false |
| Type | `content[].type` | Typed content block discriminator used for rendering. | Observed types: string. Shapes: 6. Count: 2597. Max length: 14. | false |
| JSON | `content[].text.$json` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 2. Count: 140. | false |
| Type | `type` | Message routing discriminator already represented by the popup titlebar badges. | Observed types: string. Shapes: 75. Count: 42411. Max length: 11. | false |
| JSON | `content.$json` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array, object. Shapes: 67. Count: 173. Max items: 20. | false |
| Defs | `content.$json.$defs` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 3. Count: 5. | false |
| Executor | `content.$json.$defs.executor` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 3. Count: 5. | false |
| Task | `content.$json.$defs.task` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 3. Count: 5. | false |
| ID | `content.$json.$id` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 3. Count: 5. Max length: 89. | false |
| Schema | `content.$json.$schema` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 10. Count: 12. Max length: 57. | false |
| Acceptance Criteria | `content.$json.acceptance_criteria` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 2. Count: 3. Max items: 7. | false |
| Accessibility | `content.$json.accessibility` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 4. | false |
| Active | `content.$json.active` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 9. | false |
| Additional Properties | `content.$json.additionalProperties` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 3. Count: 5. | false |
| Agent ID | `content.$json.agentId` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 17. | false |
| Agent Type | `content.$json.agentType` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 22. | false |
| Apps | `content.$json.apps` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array, string. Shapes: 2. Count: 2. Max length: 11. Max items: 110. | false |
| Attempts | `content.$json.attempts` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 2. Count: 3. | false |
| Attribution Agent | `content.$json.attributionAgent` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 22. | false |
| Attribution Plugin | `content.$json.attributionPlugin` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 7. | false |
| Attribution Skill | `content.$json.attributionSkill` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 20. | false |
| Author | `content.$json.author` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 5. Count: 7. | false |
| Email | `content.$json.author.email` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 2. Max length: 18. | false |
| Name | `content.$json.author.name` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 5. Count: 7. Max length: 14. | false |
| URL | `content.$json.author.url` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 3. Count: 4. Max length: 33. | false |
| Bin | `content.$json.bin` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 2. Count: 2. | false |
| Codex | `content.$json.bin.codex` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 12. | false |
| Toll Free Harness | `content.$json.bin.toll-free-harness` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 16. | false |
| Bundle ID | `content.$json.bundle_id` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 2. Max length: 27. | false |
| Command | `content.$json.command` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 21. Max length: 781. | false |
| Compiler Options | `content.$json.compilerOptions` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Es Module Interop | `content.$json.compilerOptions.esModuleInterop` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 1. | false |
| Exact Optional Property Types | `content.$json.compilerOptions.exactOptionalPropertyTypes` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 1. | false |
| Force Consistent Casing In File Names | `content.$json.compilerOptions.forceConsistentCasingInFileNames` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 1. | false |
| Module | `content.$json.compilerOptions.module` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 8. | false |
| Module Resolution | `content.$json.compilerOptions.moduleResolution` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 8. | false |
| No Unchecked Indexed Access | `content.$json.compilerOptions.noUncheckedIndexedAccess` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 1. | false |
| Out Dir | `content.$json.compilerOptions.outDir` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 4. | false |
| Resolve JSON Module | `content.$json.compilerOptions.resolveJsonModule` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 1. | false |
| Root Dir | `content.$json.compilerOptions.rootDir` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 1. | false |
| Skip Lib Check | `content.$json.compilerOptions.skipLibCheck` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 1. | false |
| Strict | `content.$json.compilerOptions.strict` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 1. | false |
| Target | `content.$json.compilerOptions.target` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 6. | false |
| Types | `content.$json.compilerOptions.types` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 1. Count: 1. Max items: 2. | false |
| Criteria | `content.$json.criteria` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 1. Count: 1. Max items: 3. | false |
| Current Space ID | `content.$json.current_space_id` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: null. Shapes: 2. Count: 12. | false |
| CWD | `content.$json.cwd` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 2. Max length: 71. | false |
| Data | `content.$json.data` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 1. Count: 1. Max items: 1. | false |
| Default Branch Ref | `content.$json.defaultBranchRef` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Name | `content.$json.defaultBranchRef.name` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 4. | false |
| Definitions | `content.$json.definitions` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 5. Count: 5. | false |
| Absolute Path Buf | `content.$json.definitions.AbsolutePathBuf` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 2. Count: 2. | false |
| Approvals Reviewer | `content.$json.definitions.ApprovalsReviewer` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 2. Count: 2. | false |
| Ask For Approval | `content.$json.definitions.AskForApproval` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 2. Count: 2. | false |
| Byte Range | `content.$json.definitions.ByteRange` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Collaboration Mode | `content.$json.definitions.CollaborationMode` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Command Execution Approval Decision | `content.$json.definitions.CommandExecutionApprovalDecision` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Dynamic Tool Spec | `content.$json.definitions.DynamicToolSpec` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Image Detail | `content.$json.definitions.ImageDetail` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Mode Kind | `content.$json.definitions.ModeKind` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Network Access | `content.$json.definitions.NetworkAccess` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Network Policy Amendment | `content.$json.definitions.NetworkPolicyAmendment` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Network Policy Rule Action | `content.$json.definitions.NetworkPolicyRuleAction` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Personality | `content.$json.definitions.Personality` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 2. Count: 2. | false |
| Reasoning Effort | `content.$json.definitions.ReasoningEffort` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Reasoning Summary | `content.$json.definitions.ReasoningSummary` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Sandbox Mode | `content.$json.definitions.SandboxMode` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Sandbox Policy | `content.$json.definitions.SandboxPolicy` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Settings | `content.$json.definitions.Settings` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Text Element | `content.$json.definitions.TextElement` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Thread Source | `content.$json.definitions.ThreadSource` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Thread Start Source | `content.$json.definitions.ThreadStartSource` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Tool Request User Input Answer | `content.$json.definitions.ToolRequestUserInputAnswer` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Tool Request User Input Option | `content.$json.definitions.ToolRequestUserInputOption` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Tool Request User Input Question | `content.$json.definitions.ToolRequestUserInputQuestion` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Turn Environment Params | `content.$json.definitions.TurnEnvironmentParams` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 2. Count: 2. | false |
| User Input | `content.$json.definitions.UserInput` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Dependencies | `content.$json.dependencies` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 7. Count: 11. | false |
| @jackwener/opencli | `content.$json.dependencies.@jackwener/opencli` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 3. Count: 7. Max length: 6. | false |
| @opencode Ai/plugin | `content.$json.dependencies.@opencode-ai/plugin` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 6. | false |
| @opencode Ai/sdk | `content.$json.dependencies.@opencode-ai/sdk` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 3. Count: 6. Max length: 8. | false |
| Node Pty | `content.$json.dependencies.node-pty` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 6. | false |
| Openai | `content.$json.dependencies.openai` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 4. Count: 8. Max length: 7. | false |
| Toll Free Harness | `content.$json.dependencies.toll-free-harness` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 6. | false |
| Yaml | `content.$json.dependencies.yaml` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 4. Count: 8. Max length: 6. | false |
| Zod | `content.$json.dependencies.zod` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 4. Count: 8. Max length: 8. | false |
| Deps | `content.$json.deps` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 2. Count: 3. Max items: 2. | false |
| Description | `content.$json.description` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 19. Count: 27. Max length: 833. | false |
| Design Aspect | `content.$json.design_aspect` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 3. Max length: 16. | false |
| Dev Dependencies | `content.$json.devDependencies` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 5. Count: 9. | false |
| @types/node | `content.$json.devDependencies.@types/node` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 5. Count: 9. Max length: 7. | false |
| Sharp | `content.$json.devDependencies.sharp` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 7. | false |
| Tsup | `content.$json.devDependencies.tsup` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 6. | false |
| Tsx | `content.$json.devDependencies.tsx` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 4. Count: 8. Max length: 7. | false |
| Typescript | `content.$json.devDependencies.typescript` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 5. Count: 9. Max length: 6. | false |
| Vitest | `content.$json.devDependencies.vitest` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 5. Count: 9. Max length: 6. | false |
| Done Substantive | `content.$json.doneSubstantive` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 1. Count: 8. | false |
| Element Count | `content.$json.element_count` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 2. Count: 31. | false |
| Enabled | `content.$json.enabled` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 2. Count: 8. | false |
| Engines | `content.$json.engines` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 5. Count: 9. | false |
| Node | `content.$json.engines.node` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 5. Count: 9. Max length: 4. | false |
| Entrypoint | `content.$json.entrypoint` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 3. | false |
| Executor | `content.$json.executor` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 7. Max length: 34. | false |
| Exports | `content.$json.exports` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
|  | `content.$json.exports..` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Files | `content.$json.files` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 1. Count: 1. Max items: 2. | false |
| Findings | `content.$json.findings` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 2. Max length: 246. | false |
| First ID | `content.$json.first_id` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 15. | false |
| Focus | `content.$json.focus` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 5. Max length: 48. | false |
| Function | `content.$json.function` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 3. | false |
| Description | `content.$json.function.description` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 3. Max length: 387. | false |
| Name | `content.$json.function.name` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 3. Max length: 7. | false |
| Parameters | `content.$json.function.parameters` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 3. | false |
| Funnel | `content.$json.funnel` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 17. | false |
| Git Branch | `content.$json.gitBranch` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 4. | false |
| Graph ID | `content.$json.graphId` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 16. | false |
| Groups | `content.$json.groups` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 1. Count: 8. Max items: 104. | false |
| Has More | `content.$json.has_more` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 1. | false |
| Height | `content.$json.height` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 1. Count: 1. | false |
| Homepage | `content.$json.homepage` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 4. Count: 6. Max length: 67. | false |
| Homepage URL | `content.$json.homepageUrl` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. | false |
| Human Gate | `content.$json.human_gate` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 2. Count: 3. | false |
| Idea | `content.$json.idea` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 15. | false |
| Include | `content.$json.include` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 1. Count: 1. Max items: 2. | false |
| Inputs | `content.$json.inputs` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 1. Count: 3. Max items: 4. | false |
| Interface | `content.$json.interface` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 2. Count: 3. | false |
| Brand Color | `content.$json.interface.brandColor` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 3. Max length: 7. | false |
| Capabilities | `content.$json.interface.capabilities` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 2. Count: 3. Max items: 3. | false |
| Category | `content.$json.interface.category` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 3. Max length: 12. | false |
| Composer Icon | `content.$json.interface.composerIcon` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 3. Max length: 35. | false |
| Default Prompt | `content.$json.interface.defaultPrompt` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 2. Count: 3. Max items: 3. | false |
| Developer Name | `content.$json.interface.developerName` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 3. Max length: 6. | false |
| Display Name | `content.$json.interface.displayName` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 3. Max length: 7. | false |
| Logo | `content.$json.interface.logo` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 3. Max length: 26. | false |
| Long Description | `content.$json.interface.longDescription` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 3. Max length: 575. | false |
| Privacy Policy URL | `content.$json.interface.privacyPolicyURL` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 3. Max length: 85. | false |
| Screenshots | `content.$json.interface.screenshots` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 2. Count: 3. | false |
| Short Description | `content.$json.interface.shortDescription` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 3. Max length: 41. | false |
| Terms Of Service URL | `content.$json.interface.termsOfServiceURL` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 3. Max length: 75. | false |
| Website URL | `content.$json.interface.websiteURL` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 3. Max length: 19. | false |
| Is Archived | `content.$json.isArchived` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 1. | false |
| Is Sidechain | `content.$json.isSidechain` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 1. | false |
| Keywords | `content.$json.keywords` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 4. Count: 6. Max items: 7. | false |
| Last Reason | `content.$json.lastReason` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: null. Shapes: 3. Count: 7. | false |
| Last Error | `content.$json.last_error` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: null. Shapes: 2. Count: 8. | false |
| Last ID | `content.$json.last_id` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 15. | false |
| Last Video Path | `content.$json.last_video_path` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: null, string. Shapes: 2. Count: 8. Max length: 36. | false |
| License | `content.$json.license` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 5. Count: 7. Max length: 14. | false |
| Main | `content.$json.main` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 15. | false |
| Max Attempts | `content.$json.max_attempts` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 2. Count: 3. | false |
| MCP | `content.$json.mcp` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Message | `content.$json.message` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object, string. Shapes: 2. Count: 22. Max length: 820. | false |
| Content | `content.$json.message.content` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 1. Count: 1. Max items: 1. | false |
| Diagnostics | `content.$json.message.diagnostics` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: null. Shapes: 1. Count: 1. | false |
| ID | `content.$json.message.id` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 28. | false |
| Model | `content.$json.message.model` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 15. | false |
| Role | `content.$json.message.role` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 9. | false |
| Stop Details | `content.$json.message.stop_details` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: null. Shapes: 1. Count: 1. | false |
| Stop Reason | `content.$json.message.stop_reason` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 8. | false |
| Stop Sequence | `content.$json.message.stop_sequence` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: null. Shapes: 1. Count: 1. | false |
| Type | `content.$json.message.type` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 7. | false |
| Usage | `content.$json.message.usage` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Mode | `content.$json.mode` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 8. | false |
| Model | `content.$json.model` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 20. | false |
| Name | `content.$json.name` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 20. Count: 30. Max length: 54. | false |
| Name With Owner | `content.$json.nameWithOwner` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 12. | false |
| Next Turn | `content.$json.next_turn` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 2. Count: 8. | false |
| Nodes | `content.$json.nodes` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 2. Count: 4. Max items: 12. | false |
| Object | `content.$json.object` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 4. | false |
| Output Dir | `content.$json.output_dir` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: null, string. Shapes: 2. Count: 8. Max length: 22. | false |
| Outputs | `content.$json.outputs` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 1. Count: 3. Max items: 3. | false |
| Owner | `content.$json.owner` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: null, object, string. Shapes: 4. Count: 10. Max length: 28. | false |
| Email | `content.$json.owner.email` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 20. | false |
| Name | `content.$json.owner.name` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 2. Max length: 14. | false |
| Parent UUID | `content.$json.parentUuid` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 36. | false |
| Payback Bar | `content.$json.payback_bar` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 1. Count: 1. | false |
| Permission | `content.$json.permission` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| External Directory | `content.$json.permission.external_directory` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| PID | `content.$json.pid` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 3. Count: 33. | false |
| Plan File | `content.$json.plan_file` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 59. | false |
| Plugin | `content.$json.plugin` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 1. Count: 1. Max items: 2. | false |
| Plugins | `content.$json.plugins` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 2. Count: 2. Max items: 3. | false |
| Price Hint | `content.$json.priceHint` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 2. Max length: 24. | false |
| Primary Language | `content.$json.primaryLanguage` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Name | `content.$json.primaryLanguage.name` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 4. | false |
| Private | `content.$json.private` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 1. | false |
| Properties | `content.$json.properties` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 8. Count: 10. | false |
| Answers | `content.$json.properties.answers` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Approval Policy | `content.$json.properties.approvalPolicy` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 2. Count: 2. | false |
| Approvals Reviewer | `content.$json.properties.approvalsReviewer` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 2. Count: 2. | false |
| Base Instructions | `content.$json.properties.baseInstructions` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Capabilities | `content.$json.properties.capabilities` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Config | `content.$json.properties.config` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| CWD | `content.$json.properties.cwd` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 2. Count: 2. | false |
| Decision | `content.$json.properties.decision` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Developer Instructions | `content.$json.properties.developerInstructions` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Effort | `content.$json.properties.effort` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Ephemeral | `content.$json.properties.ephemeral` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Input | `content.$json.properties.input` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Item ID | `content.$json.properties.itemId` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Model | `content.$json.properties.model` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 2. Count: 2. | false |
| Model Provider | `content.$json.properties.modelProvider` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Nodes | `content.$json.properties.nodes` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 3. Count: 5. | false |
| Output Schema | `content.$json.properties.outputSchema` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Personality | `content.$json.properties.personality` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 2. Count: 2. | false |
| Plan File | `content.$json.properties.plan_file` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 2. | false |
| Questions | `content.$json.properties.questions` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Sandbox | `content.$json.properties.sandbox` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Sandbox Policy | `content.$json.properties.sandboxPolicy` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Service Name | `content.$json.properties.serviceName` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Service Tier | `content.$json.properties.serviceTier` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 2. Count: 2. | false |
| Session Start Source | `content.$json.properties.sessionStartSource` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Summary | `content.$json.properties.summary` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Thread ID | `content.$json.properties.threadId` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 2. Count: 2. | false |
| Thread Source | `content.$json.properties.threadSource` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Turn ID | `content.$json.properties.turnId` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Variables | `content.$json.properties.variables` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 2. | false |
| Version | `content.$json.properties.version` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 3. Count: 5. | false |
| Recording | `content.$json.recording` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 2. Count: 8. | false |
| Remaining Substantive | `content.$json.remainingSubstantive` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 1. Count: 8. | false |
| Renames | `content.$json.renames` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 1. Count: 1. Max items: 35. | false |
| Repo Abs | `content.$json.repoAbs` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 8. Max length: 84. | false |
| Repository | `content.$json.repository` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object, string. Shapes: 5. Count: 7. Max length: 67. | false |
| Directory | `content.$json.repository.directory` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 9. | false |
| Type | `content.$json.repository.type` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 2. Max length: 3. | false |
| URL | `content.$json.repository.url` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 2. Max length: 52. | false |
| Request ID | `content.$json.requestId` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 28. | false |
| Required | `content.$json.required` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 7. Count: 9. Max items: 4. | false |
| Role | `content.$json.role` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 7. Max length: 7. | false |
| Salt | `content.$json.salt` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 75. | false |
| Scale Factor | `content.$json.scale_factor` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 1. Count: 1. | false |
| Scope | `content.$json.scope` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 2. Max length: 67. | false |
| Screen Recording | `content.$json.screen_recording` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 4. | false |
| Screen Recording Capturable | `content.$json.screen_recording_capturable` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 4. | false |
| Screenshot File Path | `content.$json.screenshot_file_path` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 22. Max length: 172. | false |
| Screenshot Height | `content.$json.screenshot_height` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 1. Count: 22. | false |
| Screenshot Width | `content.$json.screenshot_width` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 1. Count: 22. | false |
| Scripts | `content.$json.scripts` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 5. Count: 9. | false |
| Build | `content.$json.scripts.build` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 122. | false |
| Funnel | `content.$json.scripts.funnel` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 3. Max length: 17. | false |
| Idea | `content.$json.scripts.idea` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 3. Max length: 15. | false |
| Test | `content.$json.scripts.test` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 5. Count: 9. Max length: 10. | false |
| Typecheck | `content.$json.scripts.typecheck` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 5. Count: 9. Max length: 12. | false |
| Seed Prices | `content.$json.seed_prices` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 1. Count: 1. Max items: 3. | false |
| Self Activation Suppressed | `content.$json.self_activation_suppressed` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 2. | false |
| Session | `content.$json.session` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 10. Max length: 36. | false |
| Session ID | `content.$json.sessionId` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 36. | false |
| Significance Cutoff | `content.$json.significance_cutoff` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 1. Count: 1. | false |
| Skills | `content.$json.skills` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 3. Max length: 9. | false |
| Slug | `content.$json.slug` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 24. | false |
| Source | `content.$json.source` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 4. | false |
| Attribution | `content.$json.source.attribution` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 4. Max length: 13. | false |
| Executable | `content.$json.source.executable` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 4. Max length: 53. | false |
| Note | `content.$json.source.note` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 4. Max length: 116. | false |
| PID | `content.$json.source.pid` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 1. Count: 4. | false |
| Responsible PPID | `content.$json.source.responsible_ppid` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 1. Count: 4. | false |
| Status | `content.$json.status` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 5. Count: 11. Max length: 8. | false |
| Subagent(amplify:browser Use Chrome Devtools) | `content.$json.subagent(amplify:browser-use-chrome-devtools)` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 15. | false |
| Subagent(amplify:computer Use) | `content.$json.subagent(amplify:computer-use)` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 12. | false |
| Subnodes | `content.$json.subnodes` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| 0 | `content.$json.subnodes.t1-appendix-c.audit.0` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| 1 | `content.$json.subnodes.t1-appendix-c.audit.1` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Impl | `content.$json.subnodes.t1-appendix-c.impl` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Resolve | `content.$json.subnodes.t1-appendix-c.resolve` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Impl | `content.$json.subnodes.t2-merge-approval.impl` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Resolve | `content.$json.subnodes.t2-merge-approval.resolve` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Summary | `content.$json.summary` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 2. Max length: 76. | false |
| Target Subreddit | `content.$json.targetSubreddit` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 2. Max length: 8. | false |
| Task | `content.$json.task` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 3. Count: 8. Max length: 27. | false |
| Task ID | `content.$json.task_id` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 21. Max length: 17. | false |
| Task Type | `content.$json.task_type` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 21. Max length: 11. | false |
| Tasks | `content.$json.tasks` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| T1 Appendix C | `content.$json.tasks.t1-appendix-c` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| T2 Merge Approval | `content.$json.tasks.t2-merge-approval` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Test | `content.$json.test` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 10. | false |
| Timestamp | `content.$json.timestamp` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 24. | false |
| Title | `content.$json.title` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 9. Count: 12. Max length: 40. | false |
| Tool Use ID | `content.$json.toolUseId` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 30. | false |
| Total Substantive | `content.$json.totalSubstantive` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 1. Count: 8. | false |
| Total Trivial | `content.$json.totalTrivial` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 1. Count: 8. | false |
| Tree Markdown | `content.$json.tree_markdown` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 31. Max length: 10511. | false |
| Type | `content.$json.type` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 16. Count: 24. Max length: 9. | false |
| Typecheck | `content.$json.typecheck` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 12. | false |
| Types | `content.$json.types` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 17. | false |
| URL | `content.$json.url` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 31. | false |
| User Type | `content.$json.userType` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 8. | false |
| UUID | `content.$json.uuid` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 36. | false |
| Variables | `content.$json.variables` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| AMPLIFY CHROME DEVTOOLS AVAILABLE | `content.$json.variables.$AMPLIFY_CHROME_DEVTOOLS_AVAILABLE` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 1. | false |
| AMPLIFY CODEX AVAILABLE | `content.$json.variables.$AMPLIFY_CODEX_AVAILABLE` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 1. | false |
| AMPLIFY COMPUTER USE AVAILABLE | `content.$json.variables.$AMPLIFY_COMPUTER_USE_AVAILABLE` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 1. | false |
| AMPLIFY CUA AVAILABLE | `content.$json.variables.$AMPLIFY_CUA_AVAILABLE` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 1. | false |
| AMPLIFY KIMI AVAILABLE | `content.$json.variables.$AMPLIFY_KIMI_AVAILABLE` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 1. | false |
| AMPLIFY PLAYWRIGHT AVAILABLE | `content.$json.variables.$AMPLIFY_PLAYWRIGHT_AVAILABLE` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 1. Count: 1. | false |
| AMPLIFY USE CODEX APPROVED | `content.$json.variables.$AMPLIFY_USE_CODEX_APPROVED` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: null. Shapes: 1. Count: 1. | false |
| AMPLIFY USE KIMI APPROVED | `content.$json.variables.$AMPLIFY_USE_KIMI_APPROVED` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: null. Shapes: 1. Count: 1. | false |
| Verdict | `content.$json.verdict` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 2. Max length: 4. | false |
| Version | `content.$json.version` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 13. Count: 19. Max length: 12. | false |
| Video Active | `content.$json.video_active` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: bool. Shapes: 2. Count: 8. | false |
| Visibility | `content.$json.visibility` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 1. Max length: 6. | false |
| Width | `content.$json.width` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 1. Count: 1. | false |
| Window ID | `content.$json.window_id` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 2. Count: 31. | false |
| Windows | `content.$json.windows` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 3. Count: 14. Max items: 88. | false |
| X | `content.$json.x` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 1. Count: 1. | false |
| Y | `content.$json.y` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 1. Count: 1. | false |
| Acceptance Criteria Items | `content.$json.acceptance_criteria[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 13. Max length: 193. | false |
| Apps Items | `content.$json.apps[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 10. | false |
| Criteria Items | `content.$json.criteria[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 3. | false |
| Data Items | `content.$json.data[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 1. | false |
| Deps Items | `content.$json.deps[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 2. Max length: 12. | false |
| Files Items | `content.$json.files[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 2. Max length: 12. | false |
| Groups Items | `content.$json.groups[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 80. | false |
| Include Items | `content.$json.include[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 2. Max length: 14. | false |
| Inputs Items | `content.$json.inputs[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 6. Max length: 15. | false |
| Keywords Items | `content.$json.keywords[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 4. Count: 31. Max length: 14. | false |
| Nodes Items | `content.$json.nodes[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 2. Count: 21. | false |
| Outputs Items | `content.$json.outputs[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 5. Max length: 15. | false |
| Plugin Items | `content.$json.plugin[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 2. Max length: 102. | false |
| Plugins Items | `content.$json.plugins[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 2. Count: 4. | false |
| Renames Items | `content.$json.renames[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 10. | false |
| Required Items | `content.$json.required[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 7. Count: 22. Max length: 9. | false |
| Seed Prices Items | `content.$json.seed_prices[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 1. Count: 3. | false |
| Windows Items | `content.$json.windows[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object. Shapes: 1. Count: 56. | false |
| JSON Items | `content.$json[]` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: object, string. Shapes: 6. Count: 55. Max length: 20. | false |
| Audit Prompt | `content.$json[].audit_prompt` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 2. Max length: 5356. | false |
| Code | `content.$json[].code` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 10. Max length: 879. | false |
| Defines | `content.$json[].defines` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 2. Count: 20. Max items: 7. | false |
| Dependents | `content.$json[].dependents` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 1. Count: 10. | false |
| Deps | `content.$json[].deps` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 2. Count: 20. Max items: 3. | false |
| Description | `content.$json[].description` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 4. Max length: 68. | false |
| Executor | `content.$json[].executor` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 2. Max length: 25. | false |
| Focus | `content.$json[].focus` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 2. Max length: 32. | false |
| Gid | `content.$json[].gid` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: number. Shapes: 1. Count: 10. | false |
| Kind | `content.$json[].kind` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 20. Max length: 10. | false |
| Modules | `content.$json[].modules` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: array. Shapes: 1. Count: 10. Max items: 6. | false |
| Name | `content.$json[].name` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 2. Count: 20. Max length: 3. | false |
| Name With Owner | `content.$json[].nameWithOwner` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 4. Max length: 33. | false |
| Visibility | `content.$json[].visibility` | Reserved parsed-detail path; keep in Metadata or Raw rather than the Content form. | Observed types: string. Shapes: 1. Count: 4. Max length: 7. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Is Error | `is_error` | Read from `is_error` when present; otherwise show `Not provided`. | Render as a compact success/error state row. |
| Tool Use ID | `tool_use_id` | Read from `tool_use_id` when present; otherwise show `Not provided`. | Render as a compact copyable identifier. |
| Content | `content` | Read the raw `content` value; if it is an array, show a summary and render child blocks below. | Render string content as a complete wrapped result body in a bounded scroll area; preserve line breaks and do not add expand/collapse controls. |
| Text | `content[].text` | Read each item at `content[].text` when the content array is present. | Render inside the Content group as complete wrapped multiline text in a bounded scroll area with preserved line breaks. |
| Tool Name | `content[].tool_name` | Read each item at `content[].tool_name` when the content array is present. | Render inside the Content group as a compact scalar column. |
| Media Type | `content[].source.media_type` | Read each item at `content[].source.media_type` when the content array is present. | Render inside the Source subform as a compact media-type value. |
| Data | `content[].source.data` | Read each item at `content[].source.data` when the content array is present. | Render inside the Source subform as a media preview when possible, otherwise complete copyable data in a bounded scroll area. |

## Card Design

```text
+----------------------------------------------------------------------------+
| [User] [Tool Result]                                           [pin] [x]   |
+----------------------------------------------------------------------------+
|                         Content | Metadata | Raw                           |
+----------------------------------------------------------------------------+
| Is Error              <value from is_error>                                |
| Tool Use ID           <value from tool_use_id>                             |
| Content               <string content, or array summary when block-form>   |
|                                                                            |
| Content                                                                    |
| +-----------------------------------------------------------------------+  |
| | Text                         | Tool Name            | Source          |  |
| | <content[].text>             | <content[].tool_name>| +------------+  |  |
| |                              |                      | | Media Type | |  |
| |                              |                      | | Data       | |  |
| |                              |                      | +------------+  |  |
| +-----------------------------------------------------------------------+  |
+----------------------------------------------------------------------------+
```
