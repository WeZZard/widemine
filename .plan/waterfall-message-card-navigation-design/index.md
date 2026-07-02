# Waterfall Message Card Navigation Design

Source: `reports/claude-transcript-scans/message-type-design-array-2026-06-22.json`

This plan set was generated from the compiled Claude Code message type/subtype array. Each subtype file designs the Waterfall message navigation item and Waterfall message card for one message kind.

## Coverage

- Compiled message kinds: 53
- Required artifact pattern: `.plan/waterfall-message-card-navigation-design/{type}/{subtype}.md`
- No-subtype message kinds use `raw_event.md` as the subtype file.
- Each subtype file includes `Fields`, `Derived Car Form Content`, `Message Navigation Item Design`, and `Message Card Design`.

## Browser Verification

- Viewport: Apple Studio Display native resolution, `5120x2880`.
- Waterfall message card audit: 53 subtype samples checked, 0 issues.
- Waterfall message navigation item audit: 53 subtype samples checked, 0 issues.
- Saved screenshots:
  - [Waterfall message card](browser-verification/waterfall-message-card-final-5120x2880.png)
  - [Waterfall message navigation item](browser-verification/waterfall-navigation-item-final-5120x2880.png)
- Verified requirements:
  - Waterfall message cards render as a title bar plus content form.
  - Waterfall title bars show category badges, time, Raw, and Copy JSON actions.
  - Waterfall navigation items render as two lines: category/time, then summary.
  - All category badges have non-transparent category colors.
  - The user image card labels its image field as `Image`.
  - No old Waterfall summary/title-row layout remains.

## Message Kinds

### Agent Name
- [Agent Name](agent-name/raw_event.md) - 1761 samples

### AI Title
- [AI Title](ai-title/raw_event.md) - 3386 samples

### Assistant
- [Assistant / Message](assistant/message.md) - 40630 samples
- [Assistant / Reasoning](assistant/reasoning.md) - 6259 samples
- [Assistant / Tool Call](assistant/tool_call.md) - 43599 samples

### Attachment
- [Attachment / Agent Listing Delta](attachment/agent_listing_delta.md) - 86 samples
- [Attachment / Auto Mode](attachment/auto_mode.md) - 10 samples
- [Attachment / Auto Mode Exit](attachment/auto_mode_exit.md) - 10 samples
- [Attachment / Command Permissions](attachment/command_permissions.md) - 233 samples
- [Attachment / Compact File Reference](attachment/compact_file_reference.md) - 8 samples
- [Attachment / Date Change](attachment/date_change.md) - 38 samples
- [Attachment / Deferred Tools Delta](attachment/deferred_tools_delta.md) - 3028 samples
- [Attachment / Edited Text File](attachment/edited_text_file.md) - 235 samples
- [Attachment / File](attachment/file.md) - 37 samples
- [Attachment / Goal Status](attachment/goal_status.md) - 3 samples
- [Attachment / Hook Additional Context](attachment/hook_additional_context.md) - 2421 samples
- [Attachment / Hook Blocking Error](attachment/hook_blocking_error.md) - 1 samples
- [Attachment / Hook Non Blocking Error](attachment/hook_non_blocking_error.md) - 13 samples
- [Attachment / Hook Success](attachment/hook_success.md) - 467 samples
- [Attachment / Invoked Skills](attachment/invoked_skills.md) - 9 samples
- [Attachment / MCP Instructions Delta](attachment/mcp_instructions_delta.md) - 100 samples
- [Attachment / Nested Memory](attachment/nested_memory.md) - 29 samples
- [Attachment / Plan File Reference](attachment/plan_file_reference.md) - 9 samples
- [Attachment / Plan Mode](attachment/plan_mode.md) - 172 samples
- [Attachment / Plan Mode Exit](attachment/plan_mode_exit.md) - 138 samples
- [Attachment / Plan Mode Reentry](attachment/plan_mode_reentry.md) - 64 samples
- [Attachment / Queued Command](attachment/queued_command.md) - 356 samples
- [Attachment / Skill Listing](attachment/skill_listing.md) - 3061 samples
- [Attachment / Task Reminder](attachment/task_reminder.md) - 1045 samples
- [Attachment / Task Status](attachment/task_status.md) - 6 samples
- [Attachment / Todo Reminder](attachment/todo_reminder.md) - 493 samples
- [Attachment / Ultra Effort Enter](attachment/ultra_effort_enter.md) - 6 samples
- [Attachment / Ultra Effort Exit](attachment/ultra_effort_exit.md) - 1 samples

### Bridge Session
- [Bridge Session](bridge-session/raw_event.md) - 387 samples

### File History Snapshot
- [File History Snapshot](file-history-snapshot/raw_event.md) - 1919 samples

### Last Prompt
- [Last Prompt](last-prompt/raw_event.md) - 3682 samples

### Mode
- [Mode](mode/raw_event.md) - 2865 samples

### Permission Mode
- [Permission Mode](permission-mode/raw_event.md) - 2936 samples

### Queue Operation
- [Queue Operation](queue-operation/raw_event.md) - 13436 samples

### Result
- [Result](result/raw_event.md) - 1846 samples

### Started
- [Started](started/raw_event.md) - 2120 samples

### System
- [System / API Error](system/api_error.md) - 27 samples
- [System / Away Summary](system/away_summary.md) - 97 samples
- [System / Bridge Status](system/bridge_status.md) - 5 samples
- [System / Compact Boundary](system/compact_boundary.md) - 19 samples
- [System / Informational](system/informational.md) - 4 samples
- [System / Local Command](system/local_command.md) - 78 samples
- [System / Scheduled Task Fire](system/scheduled_task_fire.md) - 11 samples
- [System / Stop Hook Summary](system/stop_hook_summary.md) - 1374 samples
- [System / Turn Duration](system/turn_duration.md) - 949 samples

### User
- [User / Image](user/image.md) - 40 samples
- [User / Message](user/message.md) - 7827 samples
- [User / Tool Result](user/tool_result.md) - 43562 samples
