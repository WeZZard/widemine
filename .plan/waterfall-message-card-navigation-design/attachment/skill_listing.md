# Attachment / Skill Listing

## Fields
| Field | Purpose | Contents | Key | Summary |
|---|---|---|---|---|
| `content` | Visible skill listing text for preview and expansion. | Required string; count 3061; max length 8135; dash-separated skill names with descriptions. | true | true |
| `isInitial` | Initial-listing state marker. | Required boolean; count 3061; observed sample `true`. | false | false |
| `names` | Skill-name array used for counted skill rows when present. | Optional array; present in 2985 messages; max 37 items. | true | false |
| `names[]` | Repeated visible skill name. | String array item; 29850 observed items; max length 27; samples include `linear-cli` and `product-planning`. | true | false |
| `skillCount` | Visible count of listed skills. | Required number; count 3061; samples include `26`, `31`, `32`, `34`, `35`, `36`, and `37`. | true | false |
| `type` | Attachment subtype discriminator. | Required constant string `skill_listing`; rendered as the Skill Listing badge. | false | false |

## Derived Car Form Content
| Form Field | Source Field | Contents |
|---|---|---|
| Content | `content` | Skill listing text. |
| Names | `names` | Skill-name array. |
| Name | `names[]` | Skill name. |
| Skill Count | `skillCount` | Skill count. |

## Message Navigation Item Design
```text
Attachment / Skill Listing                                             14:32:07
- linear-cli: Manage Linear issues and projects from the command line...
```

Use `content` for the second-line summary, clipped to one line. The first line keeps the category and subtype together on the left, leaves flexible spacer room, and right-aligns the timestamp.

## Message Card Design
```text
+--------------------------------------------------------------------------------+
| Attachment / Skill Listing  14:32:07  agent/path              [Raw] [Copy JSON]|
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
|  Summary                                                                       |
|  +--------------------------------------------------------------------------+  |
|  | Content                                                                  |  |
|  | - linear-cli: Manage Linear issues and projects from the command line.   |  |
|  | - product-planning: Facilitate product thinking and structure work...    |  |
|  | ...                                                                      |  |
|  +--------------------------------------------------------------------------+  |
|                                                                                |
|  Skills                                                                        |
|  +-------------+------------------------------------------------------------+  |
|  | Skill Count | 32                                                         |  |
|  +-------------+------------------------------------------------------------+  |
|                                                                                |
|  Names                                                                         |
|  +----+--------------------+                                                 |
|  | #  | Name               |                                                 |
|  +----+--------------------+                                                 |
|  | 1  | linear-cli         |                                                 |
|  | 2  | product-planning   |                                                 |
|  | 3  | done               |                                                 |
|  | ...| ...                |                                                 |
|  +----+--------------------+                                                 |
|                                                                                |
|  When `names` is absent, keep the Skills count row and omit the Names table.   |
|  Raw opens formatted raw JSON for this timeline item; Copy JSON copies it.    |
+--------------------------------------------------------------------------------+
```
