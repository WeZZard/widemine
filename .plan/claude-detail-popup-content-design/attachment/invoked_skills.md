# Detail Popup Content Design - Attachment / Invoked Skills

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Skills | `skills` | Contains the invoked skill records shown by this attachment. | Array present in 9 messages; examples show `array(3 items)` and the shape observed up to 5 items. | true |
| Skills[] | `skills[]` | Represents one invoked skill record within the skills array. | Object item observed 21 times across the sample set. | false |
| Name | `skills[].name` | Identifies each invoked skill in the attachment payload. | String skill identifiers such as `amplify:brainstorming`, `amplify:execute-plan`, and `amplify:write-plan`; observed max length 21. | true |
| Content | `skills[].content` | Provides the loaded instruction body for each invoked skill. | String content containing the base directory and skill instructions; observed max length 18283. | true |
| Path | `skills[].path` | Records the plugin or skill reference path for traceability. | String path values such as `plugin:amplify:brainstorming`; observed max length 28. | false |
| Type | `type` | Routes the raw attachment payload to the invoked skills subtype. | String discriminator with observed value `invoked_skills`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Skills | `skills` | Top-level array value. | Render as a nested Skills group with one row per `skills[]` item in source order. |
| Name | `skills[].name` | Direct value from each `skills[]` item `name`. | Render as the first column in the nested Skills table. |
| Content | `skills[].content` | Direct value from each `skills[]` item `content`. | Render as the second column in the nested Skills table; preserve line breaks inside the scrollable cell with no expand/collapse control. |

## Card Design

```text
+--------------------------------------------------------------------------------+
| [Attachment] [Invoked Skills]                                         [pin] [x] |
+--------------------------------------------------------------------------------+
|                            Content | Metadata | Raw                            |
+--------------------------------------------------------------------------------+
| Skills                                                                         |
| +------------------------+---------------------------------------------------+ |
| | Name                   | Content                                           | |
| +------------------------+---------------------------------------------------+ |
| | amplify:brainstorming  | Base directory for this skill: /Users/wezzard/... | |
| |                        | # Brainstorming Ideas Into Designs ...          | |
| | amplify:execute-plan   | Base directory for this skill: /Users/wezzard/... | |
| |                        | # Executing Plans ...                           | |
| +------------------------+---------------------------------------------------+ |
+--------------------------------------------------------------------------------+
```
