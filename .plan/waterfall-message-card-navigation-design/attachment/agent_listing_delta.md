# Attachment / Agent Listing Delta

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| `addedLines` | Added agent display lines for the positive delta list. | Required array; observed in 86 messages; max 18 items. | true | false |
| `addedLines[]` | Individual added agent display line. | String array item; 833 observed items; max length 1,121; samples include `- amplify:audit-resolver: Resolve the auditor panel...`, `- claude: Catch-all for any task...`, and `- amplify:computer-use-cua: Drive the trycua/cua...`. | true | false |
| `addedTypes` | Added agent type identifiers for the main delta result. | Required array; observed in 86 messages; max 18 items. | true | true |
| `addedTypes[]` | Individual added agent type identifier. | String array item; 833 observed items; max length 35; samples include `amplify:audit-resolver`, `claude`, and `amplify:computer-use-cua`. | true | false |
| `isInitial` | Initial-listing state marker. | Required boolean; observed in 86 messages; samples include `true` and `false`. | false | false |
| `removedTypes` | Removed agent type identifiers for the negative delta list. | Required array; observed in 86 messages; sampled arrays are empty. | true | false |
| `removedTypes[]` | Individual removed agent type identifier. | Array item path for removed agent types; no item values were observed in this scan because sampled `removedTypes` arrays are empty. | true | false |
| `showConcurrencyNote` | Concurrency note display flag. | Required boolean; observed in 86 messages; sample value `true`. | false | false |
| `type` | Attachment subtype discriminator. | Required string; constant sample `agent_listing_delta`. | false | false |

## Derived Car Form Content

| Field | Source Field | Contents |
| --- | --- | --- |
| Added Lines | `addedLines` | Added agent display lines. |
| Added Line | `addedLines[]` | Individual added agent display line. |
| Added Types | `addedTypes` | Added agent type identifiers. |
| Added Type | `addedTypes[]` | Individual added agent type identifier. |
| Removed Types | `removedTypes` | Removed agent type identifiers. |
| Removed Type | `removedTypes[]` | Individual removed agent type identifier. |

## Message Navigation Item Design

```text
Attachment / Agent Listing Delta ....................................... 14:32:07
Added types: 18 | Removed types: 0 | Initial: true
```

Use the attachment-teal tone and render both category levels as full badges where badges are available. The first line keeps `Attachment / Agent Listing Delta` on the left and right-aligns the timestamp. The second line uses compact counts from `addedTypes` and `removedTypes`, then appends `isInitial` when true; keep added and removed counts separate.

## Message Card Design

```text
+--------------------------------------------------------------------------------+
| Title Bar                                                                      |
| o  [Attachment] [Agent Listing Delta]  14:32:07  agent/path  [Raw] [Copy JSON] |
+--------------------------------------------------------------------------------+
| Content Form                                                                   |
|                                                                                |
| Delta Summary                                                                  |
| +-----------------------+----------------------------------------------------+ |
| | Added Types           | 18                                                 | |
| | Added Lines           | 18                                                 | |
| | Removed Types         | 0                                                  | |
| | Initial               | true                                               | |
| | Show Concurrency Note | true                                               | |
| | Type                  | agent_listing_delta                                | |
| +-----------------------+----------------------------------------------------+ |
|                                                                                |
| Added                                                                          |
| +----+--------------------------------+--------------------------------------+ |
| | #  | addedTypes[]                   | addedLines[]                         | |
| +----+--------------------------------+--------------------------------------+ |
| | 1  | amplify:audit-resolver         | - amplify:audit-resolver: Resolve... | |
| | 2  | claude                         | - claude: Catch-all for any task...  | |
| | 3  | amplify:computer-use-cua       | - amplify:computer-use-cua: Drive... | |
| | ...| ...                            | ...                                  | |
| +----+--------------------------------+--------------------------------------+ |
|                                                                                |
| Removed                                                                        |
| +----+--------------------------------+--------------------------------------+ |
| | #  | removedTypes[]                 | State                                | |
| +----+--------------------------------+--------------------------------------+ |
| | -  | none observed                  | sampled arrays are empty             | |
| +----+--------------------------------+--------------------------------------+ |
|                                                                                |
| Notes                                                                          |
| +-----------------------+----------------------------------------------------+ |
| | showConcurrencyNote   | Show the concurrency note when true.              | |
| | isInitial             | Mark the delta as the initial listing when true.  | |
| +-----------------------+----------------------------------------------------+ |
+--------------------------------------------------------------------------------+
```

Render `addedTypes[]` and `addedLines[]` together in a nested Added table because each identifier has a matching display line. Render `removedTypes[]` as a separate nested Removed table, including the empty observed state, so removals do not collapse into the added-agent list. Keep `type`, `isInitial`, and `showConcurrencyNote` in the summary/notes area rather than mixing them into the repeated delta rows.
