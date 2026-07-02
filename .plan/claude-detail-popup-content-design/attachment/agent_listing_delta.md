# Detail Popup Content Design - Attachment / Agent Listing Delta

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Added Lines | `addedLines` | Holds the array envelope for agent listing lines added by the delta. | Array of strings; observed up to 18 items; item values appear at `addedLines[]`. | true |
| Added Lines Item | `addedLines[]` | Carries each newly added agent listing line. | String items; 833 observed; max length 1121; examples begin with `- amplify:audit-resolver`, `- claude`, and `- amplify:computer-use-cua`. | true |
| Added Types | `addedTypes` | Holds the array envelope for newly available agent types. | Array of strings; observed up to 18 items; item values appear at `addedTypes[]`. | true |
| Added Types Item | `addedTypes[]` | Carries each newly available agent type identifier. | String items; 833 observed; max length 35; examples include `amplify:audit-resolver`, `claude`, and `amplify:computer-use-cua`. | true |
| Is Initial | `isInitial` | Indicates whether this delta is the first observed agent listing state. | Boolean; 86 observed values; samples include `true` and `false`. | true |
| Removed Types | `removedTypes` | Holds the array envelope for agent types removed from the listing. | Array; observed in 86 records; no item path was observed in the scan. | true |
| Show Concurrency Note | `showConcurrencyNote` | Indicates whether the concurrency note should be shown with the listing delta. | Boolean; 86 observed values; sampled value is `true`. | true |
| Type | `type` | Raw attachment discriminator used for routing. | String; observed value is `agent_listing_delta`. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Added Lines | `addedLines` | Direct array from `addedLines`; item rows come from `addedLines[]`. | Render as a nested one-column `Added Lines` group; empty array renders `None`. |
| Added Lines Item | `addedLines[]` | Each string item in `addedLines`. | Render inside the `Added Lines` group under `Item`; wrap long listing descriptions and allow expansion for full text. |
| Added Types | `addedTypes` | Direct array from `addedTypes`; item rows come from `addedTypes[]`. | Render as a nested one-column `Added Types` group; empty array renders `None`. |
| Added Types Item | `addedTypes[]` | Each string item in `addedTypes`. | Render inside the `Added Types` group under `Item`; never as an unrelated top-level row. |
| Is Initial | `isInitial` | Direct boolean value from `isInitial`. | Render as a compact `true` or `false` scalar row. |
| Removed Types | `removedTypes` | Direct array from `removedTypes`; source data did not expose a populated `removedTypes[]` item path. | Render as a nested one-column `Removed Types` group; empty array renders `None`, otherwise show one type identifier per row. |
| Show Concurrency Note | `showConcurrencyNote` | Direct boolean value from `showConcurrencyNote`. | Render as a compact `true` or `false` scalar row. |

## Card Design

```text
+----------------------------------------------------------------------------+
| [Attachment] [Agent Listing Delta]                              [pin] [x] |
+----------------------------------------------------------------------------+
|                         Content | Metadata | Raw                           |
+----------------------------------------------------------------------------+
| Added Lines                                                                |
|   +--------------------------------------------------------------------+   |
|   | Item                                                               |   |
|   +--------------------------------------------------------------------+   |
|   | - amplify:audit-resolver: Resolve the auditor panel...             |   |
|   | - claude: Catch-all for any task that does not fit...              |   |
|   | ...                                                                |   |
|   +--------------------------------------------------------------------+   |
| Added Types                                                                |
|   +-----------------------------+                                          |
|   | Item                        |                                          |
|   +-----------------------------+                                          |
|   | amplify:audit-resolver      |                                          |
|   | claude                      |                                          |
|   | amplify:computer-use-cua    |                                          |
|   +-----------------------------+                                          |
| Is Initial                   true                                           |
| Removed Types                                                              |
|   +-----------------------------+                                          |
|   | Item                        |                                          |
|   +-----------------------------+                                          |
|   | None                        |                                          |
|   +-----------------------------+                                          |
| Show Concurrency Note         true                                          |
+----------------------------------------------------------------------------+
```
