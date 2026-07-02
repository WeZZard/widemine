# Result

## Fields

| Field | Purpose | Contents | Key | Summary |
| --- | --- | --- | --- | --- |
| agentId | Agent identifier that produced the workflow result. | string; count 1846; max length 17; sample agent id | true | false |
| key | Workflow result key used to correlate this result with the workflow cache or caller. | string; count 1846; max length 67; sample `v2:...` | true | false |
| result | Primary workflow result payload shown in preview and detail. | object 1838, string 8; count 1846; max string length 15057 | true | true |
| result.$json | Parsed mirror when `result` is a JSON string. | object; count 8 | false | false |
| result.$json.doneSubstantive | Parsed completed substantive count inside JSON-string results. | number; count 8; samples include `1023`, `1103`, `500`, `624` | false | false |
| result.$json.groups | Parsed group array inside JSON-string results. | array; count 8; max items 104 | false | false |
| result.$json.groups[] | Parsed group item inside JSON-string results. | object; count 80 | false | false |
| result.$json.remainingSubstantive | Parsed remaining substantive count inside JSON-string results. | number; count 8; samples include `1047`, `1319`, `568`, `648` | false | false |
| result.$json.repoAbs | Parsed repository path inside JSON-string results. | string; count 8; max length 84 | false | false |
| result.$json.totalSubstantive | Parsed total substantive count inside JSON-string results. | number; count 8; sample `1819` | false | false |
| result.$json.totalTrivial | Parsed total trivial count inside JSON-string results. | number; count 8; sample `3919` | false | false |
| result.angles | Search-angle list returned by planning style results. | array; count 1; max items 5 | true | false |
| result.angles[] | Search-angle item. | object; count 5 | true | false |
| result.angles[].label | Search-angle label. | string; count 5; max length 35 | true | false |
| result.angles[].query | Search-angle query. | string; count 5; max length 122 | true | false |
| result.angles[].rationale | Search-angle rationale. | string; count 5; max length 177 | true | false |
| result.batch | Batch number for write/progress result objects. | number; count 1077; samples include `0`, `1`, `10`, `100` | true | false |
| result.caveats | Caveats text returned by synthesis results. | string; count 1; max length 1581 | true | false |
| result.claims | Claim list returned by evidence extraction results. | array; count 20; max items 5 | true | false |
| result.claims[] | Claim item. | object; count 85 | true | false |
| result.claims[].claim | Claim text. | string; count 85; max length 407 | true | false |
| result.claims[].importance | Claim importance value. | string; count 85; max length 10; samples `central`, `supporting` | true | false |
| result.claims[].quote | Supporting quote text. | string; count 85; max length 317 | true | false |
| result.confidence | Confidence value for verification results. | string; count 75; max length 6; samples `high`, `medium` | true | false |
| result.counterSource | Counter-source text for verification results. | string; count 74; max length 390 | true | false |
| result.evidence | Evidence text for verification results. | string; count 75; max length 1860 | true | false |
| result.findings | Finding list returned by synthesis results. | array; count 1; max items 13 | true | false |
| result.findings[] | Finding item. | object; count 10 | true | false |
| result.findings[].claim | Finding claim text. | string; count 10; max length 450 | true | false |
| result.findings[].confidence | Finding confidence value. | string; count 10; max length 6; sample `high` | true | false |
| result.findings[].evidence | Finding evidence text. | string; count 10; max length 647 | true | false |
| result.findings[].sources | Finding source list. | array; count 10; max items 2 | true | false |
| result.findings[].vote | Finding vote text. | string; count 10; max length 59 | true | false |
| result.globalRenames | Top-level rename list returned by module rewrite results. | array; count 13; max items 14 | true | false |
| result.globalRenames[] | Top-level rename item. | object; count 36 | true | false |
| result.globalRenames[].doc | Rename documentation text. | string; count 36; max length 183 | true | false |
| result.globalRenames[].kind | Rename kind. | string; count 36; max length 11; samples `class`, `module-init`, `value` | true | false |
| result.globalRenames[].new | New symbol name. | string; count 36; max length 37 | true | false |
| result.globalRenames[].old | Old symbol name. | string; count 36; max length 3 | true | false |
| result.id | Module or result identifier. | string; count 18; max length 3 | true | false |
| result.issues | Issue list returned by review results. | array; count 1; max items 8 | true | false |
| result.issues[] | Issue item. | object; count 8 | true | false |
| result.issues[].detail | Issue detail text. | string; count 8; max length 666 | true | false |
| result.issues[].kind | Issue kind. | string; count 8; max length 10; sample `naming` | true | false |
| result.issues[].module | Issue module path or name. | string; count 8; max length 33 | true | false |
| result.issues[].suggestion | Issue suggestion text. | string; count 8; max length 253 | true | false |
| result.moduleSummary | Module summary text. | string; count 18; max length 745 | true | false |
| result.modules | Module result list. | array; count 640; max items 7 | true | false |
| result.modules[] | Module result item. | object; count 1670 | true | false |
| result.modules[].globalRenames | Module-local rename list. | array; count 1670; max items 31 | true | false |
| result.modules[].id | Module identifier. | string; count 1670; max length 3 | true | false |
| result.modules[].moduleSummary | Module summary text for a module result item. | string; count 1670; max length 1825 | true | false |
| result.modules[].newModuleName | Proposed or generated module name. | string; count 1670; max length 41 | true | false |
| result.modules[].rewrittenSource | Rewritten module source text. | string; count 1670; max length 115633 | true | false |
| result.newModuleName | Top-level proposed or generated module name. | string; count 18; max length 30 | true | false |
| result.notes | Review notes text. | string; count 1; max length 1360 | true | false |
| result.openQuestions | Open-question list returned by synthesis results. | array; count 1; max items 4 | true | false |
| result.openQuestions[] | Open-question item. | string; count 4; max length 261 | true | false |
| result.publishDate | Publication date or publication-date note. | string; count 20; max length 108 | true | false |
| result.question | Question text for planning results. | string; count 1; max length 656 | true | false |
| result.refuted | Refuted flag for verification results. | bool; count 75; samples `false`, `true` | true | false |
| result.results | Search result list. | array; count 5; max items 6 | true | false |
| result.results[] | Search result item. | object; count 30 | true | false |
| result.results[].relevance | Search result relevance value. | string; count 30; max length 6; sample `high` | true | false |
| result.results[].snippet | Search result snippet text. | string; count 30; max length 597 | true | false |
| result.results[].title | Search result title. | string; count 30; max length 95 | true | false |
| result.results[].url | Search result URL. | string; count 30; max length 129 | true | false |
| result.rewrittenSource | Top-level rewritten source text. | string; count 18; max length 9633 | true | false |
| result.sourceQuality | Source quality value. | string; count 20; max length 9; samples `blog`, `primary`, `secondary` | true | false |
| result.summary | Summary text returned by planning or synthesis results. | string; count 2; max length 1658 | true | false |
| result.verdict | Verdict value returned by review results. | string; count 1; max length 11; sample `needs-fixes` | true | false |
| result.written | Written count for write/progress result objects. | number; count 1077; samples include `0`, `1`, `102`, `103` | true | false |
| type | Raw event discriminator. | constant `result`; count 1846 | false | false |

## Derived Car Form Content

| Field | Contents |
| --- | --- |
| Agent ID | `{agentId}` |
| Key | `{key}` |
| Result | `{result}` |
| Angles | `{result.angles}` |
| Angle Item | `{result.angles[]}` |
| Angle Label | `{result.angles[].label}` |
| Angle Query | `{result.angles[].query}` |
| Angle Rationale | `{result.angles[].rationale}` |
| Batch | `{result.batch}` |
| Caveats | `{result.caveats}` |
| Claims | `{result.claims}` |
| Claim Item | `{result.claims[]}` |
| Claim | `{result.claims[].claim}` |
| Claim Importance | `{result.claims[].importance}` |
| Claim Quote | `{result.claims[].quote}` |
| Confidence | `{result.confidence}` |
| Counter Source | `{result.counterSource}` |
| Evidence | `{result.evidence}` |
| Findings | `{result.findings}` |
| Finding Item | `{result.findings[]}` |
| Finding Claim | `{result.findings[].claim}` |
| Finding Confidence | `{result.findings[].confidence}` |
| Finding Evidence | `{result.findings[].evidence}` |
| Finding Sources | `{result.findings[].sources}` |
| Finding Vote | `{result.findings[].vote}` |
| Global Renames | `{result.globalRenames}` |
| Global Rename Item | `{result.globalRenames[]}` |
| Global Rename Doc | `{result.globalRenames[].doc}` |
| Global Rename Kind | `{result.globalRenames[].kind}` |
| Global Rename New | `{result.globalRenames[].new}` |
| Global Rename Old | `{result.globalRenames[].old}` |
| ID | `{result.id}` |
| Issues | `{result.issues}` |
| Issue Item | `{result.issues[]}` |
| Issue Detail | `{result.issues[].detail}` |
| Issue Kind | `{result.issues[].kind}` |
| Issue Module | `{result.issues[].module}` |
| Issue Suggestion | `{result.issues[].suggestion}` |
| Module Summary | `{result.moduleSummary}` |
| Modules | `{result.modules}` |
| Module Item | `{result.modules[]}` |
| Module Global Renames | `{result.modules[].globalRenames}` |
| Module ID | `{result.modules[].id}` |
| Module Item Summary | `{result.modules[].moduleSummary}` |
| Module New Name | `{result.modules[].newModuleName}` |
| Module Rewritten Source | `{result.modules[].rewrittenSource}` |
| New Module Name | `{result.newModuleName}` |
| Notes | `{result.notes}` |
| Open Questions | `{result.openQuestions}` |
| Open Question Item | `{result.openQuestions[]}` |
| Publish Date | `{result.publishDate}` |
| Question | `{result.question}` |
| Refuted | `{result.refuted}` |
| Results | `{result.results}` |
| Result Item | `{result.results[]}` |
| Result Relevance | `{result.results[].relevance}` |
| Result Snippet | `{result.results[].snippet}` |
| Result Title | `{result.results[].title}` |
| Result URL | `{result.results[].url}` |
| Rewritten Source | `{result.rewrittenSource}` |
| Source Quality | `{result.sourceQuality}` |
| Summary | `{result.summary}` |
| Verdict | `{result.verdict}` |
| Written | `{result.written}` |

## Message Navigation Item Design

Use `Result` as the first-level category. This kind has no second-level category.

```text
Result ..................................................... {time}
{agentId} | {key} | {result}
```

Line 2 preserves the result payload as the summary source. When the payload is an object, the navigation preview should compact it to the visible object keyset plus the first present scalar value; when it is a string, show the compacted string value. Agent ID and key are correlation supports and may be truncated after the result summary has been generated.

## Message Card Design

Render the card with a compact title bar and a content form. Render only sections whose fields are present; keep the raw `result` payload available before any parsed or nested convenience tables.

```text
+-- o Result ------------------------ {time} -- {agentId} -- Raw -- Copy JSON --+
| Content Form                                                                  |
|                                                                               |
|  Result Details                                                               |
|  +------------+-------------------------------------------------------------+ |
|  | Agent ID   | {agentId}                                                   | |
|  | Key        | {key}                                                       | |
|  | Type       | {type}                                                      | |
|  +------------+-------------------------------------------------------------+ |
|                                                                               |
|  Result Payload                                                               |
|  +-------------------+------------------------------------------------------+ |
|  | Result            | {result}                                             | |
|  | Batch             | {result.batch}                                       | |
|  | Written           | {result.written}                                     | |
|  | ID                | {result.id}                                          | |
|  | New Module Name   | {result.newModuleName}                               | |
|  | Module Summary    | {result.moduleSummary}                               | |
|  | Rewritten Source  | {result.rewrittenSource}                             | |
|  | Summary           | {result.summary}                                     | |
|  | Verdict           | {result.verdict}                                     | |
|  | Confidence        | {result.confidence}                                  | |
|  | Refuted           | {result.refuted}                                     | |
|  | Evidence          | {result.evidence}                                    | |
|  | Counter Source    | {result.counterSource}                               | |
|  | Source Quality    | {result.sourceQuality}                               | |
|  | Publish Date      | {result.publishDate}                                 | |
|  | Question          | {result.question}                                    | |
|  | Caveats           | {result.caveats}                                     | |
|  | Notes             | {result.notes}                                       | |
|  +-------------------+------------------------------------------------------+ |
|                                                                               |
|  Modules                                                                      |
|  +----+-------+------------------+----------------------+-------------------+ |
|  | #  | ID    | New Module Name  | Module Summary       | Rewritten Source  | |
|  | 1  | {result.modules[].id}  | {result.modules[].newModuleName}            | |
|  |    |       |                  | {result.modules[].moduleSummary}            | |
|  |    |       |                  | {result.modules[].rewrittenSource}          | |
|  |    | Module Global Renames  | {result.modules[].globalRenames}            | |
|  +----+-------+------------------+----------------------+-------------------+ |
|                                                                               |
|  Global Renames                                                               |
|  +----+-------+----------------------+-------------+-----------------------+ |
|  | #  | Old   | New                  | Kind        | Doc                   | |
|  | 1  | {result.globalRenames[].old} | {result.globalRenames[].new}           | |
|  |    |       |                      | {result.globalRenames[].kind}          | |
|  |    |       |                      | {result.globalRenames[].doc}           | |
|  +----+-------+----------------------+-------------+-----------------------+ |
|                                                                               |
|  Claims                                                                       |
|  +----+------------+-----------------------+--------------------------------+ |
|  | #  | Importance | Claim                 | Quote                          | |
|  | 1  | {result.claims[].importance} | {result.claims[].claim}              | |
|  |    |            |                       | {result.claims[].quote}        | |
|  +----+------------+-----------------------+--------------------------------+ |
|                                                                               |
|  Search Results                                                               |
|  +----+-----------+---------------------+------------------+---------------+ |
|  | #  | Relevance | Title               | URL              | Snippet       | |
|  | 1  | {result.results[].relevance} | {result.results[].title}          | |
|  |    |           | {result.results[].url} | {result.results[].snippet}      | |
|  +----+-----------+---------------------+------------------+---------------+ |
|                                                                               |
|  Angles                                                                       |
|  +----+----------------------+-------------------------+-------------------+ |
|  | #  | Label                | Query                   | Rationale         | |
|  | 1  | {result.angles[].label} | {result.angles[].query}              | |
|  |    |                      |                         | {result.angles[].rationale} | |
|  +----+----------------------+-------------------------+-------------------+ |
|                                                                               |
|  Findings                                                                     |
|  +----+------------+-----------------------+----------------+----------------+ |
|  | #  | Confidence | Claim                 | Evidence       | Sources/Vote   | |
|  | 1  | {result.findings[].confidence} | {result.findings[].claim}        | |
|  |    |            | {result.findings[].evidence} | {result.findings[].sources} | |
|  |    |            |                       | {result.findings[].vote}        | |
|  +----+------------+-----------------------+----------------+----------------+ |
|                                                                               |
|  Issues                                                                       |
|  +----+-----------+---------------------+-------------------+----------------+ |
|  | #  | Kind      | Module              | Detail            | Suggestion     | |
|  | 1  | {result.issues[].kind} | {result.issues[].module}                 | |
|  |    |           | {result.issues[].detail} | {result.issues[].suggestion}    | |
|  +----+-----------+---------------------+-------------------+----------------+ |
|                                                                               |
|  Open Questions                                                               |
|  +----+---------------------------------------------------------------------+ |
|  | #  | Question                                                            | |
|  | 1  | {result.openQuestions[]}                                            | |
|  +----+---------------------------------------------------------------------+ |
|                                                                               |
|  Parsed JSON Result String                                                    |
|  +------------------------+--------------------------------------------------+ |
|  | Repo Abs               | {result.$json.repoAbs}                         | |
|  | Done Substantive       | {result.$json.doneSubstantive}                 | |
|  | Remaining Substantive  | {result.$json.remainingSubstantive}            | |
|  | Total Substantive      | {result.$json.totalSubstantive}                | |
|  | Total Trivial          | {result.$json.totalTrivial}                    | |
|  | Groups                 | +----+---------------------------------------+ | |
|  |                        | | #  | {result.$json.groups[]}             | | |
|  |                        | +----+---------------------------------------+ | |
|  +------------------------+--------------------------------------------------+ |
|                                                                               |
|  Raw opens formatted raw JSON for this timeline item. Copy JSON copies the    |
|  raw event, not the parsed convenience view.                                   |
+-------------------------------------------------------------------------------+
```
