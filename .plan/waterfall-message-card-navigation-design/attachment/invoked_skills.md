# Attachment / Invoked Skills Waterfall Surface Design

## Fields
| Field | Purpose | Contents | Key | Summary |
|---|---|---|---|---|
| `skills` | Skill list container and count source. | Required array; count 9; max 5 items observed. | true | false |
| `skills[]` | Repeated invoked skill item. | Object rows; 21 total observed items. | false | false |
| `skills[].content` | Skill body used for concise description and expansion. | String; max length 18283; begins with base directory and skill markdown. | true | false |
| `skills[].name` | Visible skill name. | String; max length 21; samples include `amplify:brainstorming`, `amplify:execute-plan`, and `amplify:write-plan`. | true | true |
| `skills[].path` | Skill identifier path. | String; max length 28; samples include `plugin:amplify:brainstorming`, `plugin:amplify:execute-plan`, and `plugin:amplify:write-plan`. | true | false |
| `type` | Attachment subtype discriminator. | Required constant string `invoked_skills`; rendered as the Invoked Skills badge. | false | false |

## Derived Car Form Content
| Form Field | Source Field | Control | Contents |
|---|---|---|---|
| Skills | `skills` | Counted nested table | Number of invoked skills and one row per skill. |
| Skills Content | `skills[].content` | Expandable wrapped text | Concise first meaningful content line; expand for full skill body. |
| Skills Name | `skills[].name` | Compact scalar | Visible skill name. |
| Skills Path | `skills[].path` | Compact monospace scalar | Skill identifier path. |

## Message Navigation Item Design
```text
+--------------------------------------------------------------------------------+
| o  [Attachment] [Invoked Skills]  14:32:07  amplify:brainstorming +2 skills    |
+--------------------------------------------------------------------------------+
  activity dot   full badges                     timestamp   first skill preview
  tone: attachment-teal; use the same full badge style for both category levels

Preview:
- Use the first `skills[].name` as the first meaningful content line.
- Append `+N skills` when more than one skill is present.
```

## Message Card Design
```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [Invoked Skills]  timestamp  agent/path       [Raw] [Copy JSON]|
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
|  Skills (3)                                                                    |
|  +----+------------------------+--------------------------------------------+  |
|  | #  | Skills Name            | Skills Path                                |  |
|  +----+------------------------+--------------------------------------------+  |
|  | 1  | amplify:brainstorming  | plugin:amplify:brainstorming              |  |
|  | 2  | amplify:execute-plan   | plugin:amplify:execute-plan               |  |
|  | 3  | amplify:write-plan     | plugin:amplify:write-plan                 |  |
|  +----+------------------------+--------------------------------------------+  |
|                                                                                |
|  Selected Skill                                                                |
|  +----------------+---------------------------------------------------------+  |
|  | Skills Name    | amplify:brainstorming                                  |  |
|  | Skills Path    | plugin:amplify:brainstorming                           |  |
|  | Skills Content | Base directory for this skill: /Users/...               |  |
|  |                | # Brainstorming Ideas Into Designs                     |  |
|  |                | concise description, wrapped in message typography      |  |
|  |                | [Expand skill content]                                 |  |
|  +----------------+---------------------------------------------------------+  |
|                                                                                |
|  Raw button opens formatted raw JSON for this timeline item.                   |
+--------------------------------------------------------------------------------+
```
