# Detail Popup Content Design - Attachment / Skill Listing

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Content | `content` | Carries the visible skill listing body and descriptions. | String; 2807 observed values across two shapes; dash-prefixed skill entries; observed max length 8135. | true |
| Is Initial | `isInitial` | Records whether the attachment was emitted as an initial payload state. | Boolean; 2807 observed values, all sampled as `true`. | false |
| Names | `names` | Provides the skill-name array that supports the visible listing and itemized skill display. | Array; present in the 2731-count shape, absent in the 76-count shape; observed max 37 items. | true |
| Names Item | `names[]` | Provides each individual skill name from the skill-name array. | String array item; 27310 observed items; examples include `linear-cli` and `product-planning`; observed max length 27. | true |
| Skill Count | `skillCount` | States how many skills are represented in the listing. | Number; 2807 observed values; samples include `26`, `27`, `31`, `32`, `33`, `34`, `35`, `36`, and `37`. | true |
| Type | `type` | Routes the raw attachment payload; category identity is already shown in the popup titlebar. | String; 2807 observed values with sample `skill_listing`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Content | `content` | Direct value from `content`. | Render as complete pre-wrapped multiline text with source order preserved inside a bounded scroll area; do not add expand/collapse controls. |
| Names | `names` | Direct array from `names` when present. | Render as the parent `Names` nested form group; if absent, omit the group rather than showing an empty list. |
| Names Item | `names[]` | Each scalar item from `names[]` in source order. | Render inside the `Names` group as a one-column nested table of skill names. |
| Skill Count | `skillCount` | Direct value from `skillCount`. | Render as a compact numeric row near the listing summary. |

## Card Design

```text
+------------------------------------------------------------------------------+
| [Attachment] [Skill Listing]                                      [pin] [x] |
+------------------------------------------------------------------------------+
|                         Content | Metadata | Raw                            |
+------------------------------------------------------------------------------+
| Content       - linear-cli: Manage Linear issues and projects from the       |
|               command line.                                                 |
|               - product-planning: Facilitate product thinking and structure  |
|               work in Linear.                                               |
| Skill Count   32                                                            |
| Names                                                                       |
|   +-----------------------+                                                  |
|   | Names Item            |                                                  |
|   +-----------------------+                                                  |
|   | linear-cli            |                                                  |
|   | product-planning      |                                                  |
|   | done                  |                                                  |
|   +-----------------------+                                                  |
+------------------------------------------------------------------------------+
```
