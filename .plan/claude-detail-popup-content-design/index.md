# Claude Detail Popup Content Design

This plan is regenerated from `apps/session-viewer/reports/claude-transcript-scans/message-type-design-array-2026-06-22.json` and contains one subtype file per compiled type/subtype entry.

## Popup Structure

Every subtype design targets the Timeline detailed message popup and uses exactly three visible sections:

1. Section 1: two-level category badges plus pin and close controls.
2. Section 2: centered `Content | Metadata | Raw` segmented control.
3. Section 3: the active panel selected by the segmented control.

For the Content panel, Section 3 renders derived form content directly. It must not repeat type, subtype, category text, or the two-level badges that already live in Section 1.

## Required File Template

Each subtype file uses this fixed section template:

```markdown
## Fields

## Derived Form Content

## Card Design
```

Template rules:

- `## Fields` contains a table with field name, raw path, purpose, contents, and a `Key` column whose values are only `true` or `false`.
- `## Fields` lists flattened message JSON fields from `shapes[].fields`; nested objects are represented by child paths such as `foo.fee`, `foo.foe`, and `foo.fum`.
- `Key=true` is reserved for fields strongly connected to the message purpose, mission, or result; fields that support those values; and fields whose contents can be observed by the end user.
- `Key=false` is required for Content-section metadata, routing, and trace fields, including type, subtype, timestamp, session IDs, UUIDs, version, working directory, git branch, entrypoint, user type, sidechain/meta flags, slug, line, path, file, and scan bookkeeping.
- `Key=false` is required for any field path containing a segment that starts with `__` or `$`.
- `## Derived Form Content` contains form rows based only on `Key=true` fields. Form field names are human-readable source field names without interpretation.
- `## Card Design` contains ASCII art with the three popup sections and a third section that has no form title.
- `## Card Design` groups flattened array fields into nested forms or tables. For example, `bar[].hee`, `bar[].hoe`, and `bar[].hum` appear as one `Bar` group with `Hee`, `Hoe`, and `Hum` columns, not as unrelated top-level rows.
- Long values render completely inside their own bounded scroll row or nested value block. Preserve source line breaks and do not use expand/collapse controls in the detailed popup.

## Subtype Index

### assistant

- [tool_call](assistant/tool_call.md) - 42,448 observations, 147 shape(s) - Tool call request
- [message](assistant/message.md) - 39,280 observations, 3 shape(s) - Natural-language message
- [reasoning](assistant/reasoning.md) - 6,154 observations, 1 shape(s) - Assistant reasoning content

### user

- [tool_result](user/tool_result.md) - 42,411 observations, 75 shape(s) - Tool call result
- [message](user/message.md) - 7,546 observations, 1 shape(s) - Natural-language message
- [image](user/image.md) - 40 observations, 1 shape(s) - User-provided image

### queue-operation

- [raw_event](queue-operation/raw_event.md) - 13,428 observations, 2 shape(s) - Queue operation metadata

### last-prompt

- [raw_event](last-prompt/raw_event.md) - 3,623 observations, 2 shape(s) - Last prompt metadata

### ai-title

- [raw_event](ai-title/raw_event.md) - 3,327 observations, 1 shape(s) - Session title metadata

### permission-mode

- [raw_event](permission-mode/raw_event.md) - 2,877 observations, 1 shape(s) - Permission mode metadata

### attachment

- [skill_listing](attachment/skill_listing.md) - 2,807 observations, 2 shape(s) - Available skill listing
- [deferred_tools_delta](attachment/deferred_tools_delta.md) - 2,774 observations, 7 shape(s) - Deferred tool additions and removals
- [hook_additional_context](attachment/hook_additional_context.md) - 2,398 observations, 1 shape(s) - Hook-provided execution context
- [task_reminder](attachment/task_reminder.md) - 1,022 observations, 2 shape(s) - Task reminder
- [todo_reminder](attachment/todo_reminder.md) - 493 observations, 2 shape(s) - Todo reminder
- [hook_success](attachment/hook_success.md) - 467 observations, 2 shape(s) - Successful hook result with extracted context
- [queued_command](attachment/queued_command.md) - 353 observations, 4 shape(s) - Queued command details
- [command_permissions](attachment/command_permissions.md) - 233 observations, 2 shape(s) - Command permission decision
- [edited_text_file](attachment/edited_text_file.md) - 227 observations, 1 shape(s) - Edited text file metadata
- [plan_mode](attachment/plan_mode.md) - 172 observations, 1 shape(s) - Plan mode state
- [plan_mode_exit](attachment/plan_mode_exit.md) - 138 observations, 1 shape(s) - Plan mode exit
- [mcp_instructions_delta](attachment/mcp_instructions_delta.md) - 100 observations, 2 shape(s) - MCP instruction additions and removals
- [agent_listing_delta](attachment/agent_listing_delta.md) - 86 observations, 1 shape(s) - Agent listing additions and removals
- [plan_mode_reentry](attachment/plan_mode_reentry.md) - 64 observations, 1 shape(s) - Plan mode re-entry
- [file](attachment/file.md) - 37 observations, 2 shape(s) - File attachment
- [date_change](attachment/date_change.md) - 35 observations, 1 shape(s) - Date boundary
- [nested_memory](attachment/nested_memory.md) - 29 observations, 1 shape(s) - Nested memory reference
- [hook_non_blocking_error](attachment/hook_non_blocking_error.md) - 13 observations, 1 shape(s) - Non-blocking hook failure
- [auto_mode](attachment/auto_mode.md) - 10 observations, 1 shape(s) - Auto mode entered
- [auto_mode_exit](attachment/auto_mode_exit.md) - 10 observations, 1 shape(s) - Auto mode exited
- [invoked_skills](attachment/invoked_skills.md) - 9 observations, 1 shape(s) - Invoked skill list
- [plan_file_reference](attachment/plan_file_reference.md) - 9 observations, 1 shape(s) - Plan file reference
- [compact_file_reference](attachment/compact_file_reference.md) - 8 observations, 1 shape(s) - Compact transcript file reference
- [task_status](attachment/task_status.md) - 6 observations, 1 shape(s) - Task status update
- [ultra_effort_enter](attachment/ultra_effort_enter.md) - 6 observations, 1 shape(s) - Ultra Effort mode entered
- [goal_status](attachment/goal_status.md) - 3 observations, 2 shape(s) - Goal status update
- [hook_blocking_error](attachment/hook_blocking_error.md) - 1 observations, 1 shape(s) - Blocking hook failure
- [ultra_effort_exit](attachment/ultra_effort_exit.md) - 1 observations, 1 shape(s) - Ultra Effort mode exited

### mode

- [raw_event](mode/raw_event.md) - 2,806 observations, 1 shape(s) - Mode metadata

### file-history-snapshot

- [raw_event](file-history-snapshot/raw_event.md) - 1,884 observations, 508 shape(s) - File history snapshot

### started

- [raw_event](started/raw_event.md) - 1,867 observations, 1 shape(s) - Workflow start metadata

### agent-name

- [raw_event](agent-name/raw_event.md) - 1,761 observations, 1 shape(s) - Agent identity metadata

### result

- [raw_event](result/raw_event.md) - 1,593 observations, 13 shape(s) - Workflow result metadata

### system

- [stop_hook_summary](system/stop_hook_summary.md) - 1,355 observations, 8 shape(s) - Stop hook summary
- [turn_duration](system/turn_duration.md) - 926 observations, 5 shape(s) - Turn timing summary
- [away_summary](system/away_summary.md) - 90 observations, 2 shape(s) - Away-mode summary
- [local_command](system/local_command.md) - 74 observations, 3 shape(s) - Local command caveat
- [api_error](system/api_error.md) - 27 observations, 4 shape(s) - API failure details
- [compact_boundary](system/compact_boundary.md) - 19 observations, 5 shape(s) - Compaction boundary marker
- [scheduled_task_fire](system/scheduled_task_fire.md) - 11 observations, 1 shape(s) - Scheduled task execution
- [bridge_status](system/bridge_status.md) - 5 observations, 2 shape(s) - Bridge status update
- [informational](system/informational.md) - 4 observations, 2 shape(s) - Informational system message

### bridge-session

- [raw_event](bridge-session/raw_event.md) - 339 observations, 1 shape(s) - Bridge session metadata

## Audit

- Source subtype entries: 53.
- Expected subtype files: 53.
- Expected index file: 1.
- Required headings per subtype file: `## Fields`, `## Derived Form Content`, `## Card Design`.
- Required detailed popup model: exactly three sections, with Section 3 switching between Content, Metadata, and Raw.
