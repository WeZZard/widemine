# Detail Popup Content Design - Result / Raw Event

## Fields

| Field | Raw Path | Purpose | Contents | Key |
| --- | --- | --- | --- | --- |
| Agent ID | `agentId` | Identifies the emitting workflow agent for trace correlation. | Observed types: string. Shapes: 13. Count: 1593. Max length: 17. | false |
| Key | `key` | Identifies the stored workflow result record for trace correlation. | Observed types: string. Shapes: 13. Count: 1593. Max length: 67. | false |
| Result | `result` | Carries the primary workflow result payload, including scalar raw results and structured result objects. | Observed types: object, string. Shapes: 13. Count: 1593. Max length: 15057. | true |
| JSON | `result.$json` | Parser-detected JSON object inside a scalar result string. | Observed types: object. Shapes: 1. Count: 8. | false |
| Done Substantive | `result.$json.doneSubstantive` | Parser-detected progress count inside scalar result JSON. | Observed types: number. Shapes: 1. Count: 8. | false |
| Groups | `result.$json.groups` | Parser-detected grouped result array inside scalar result JSON. | Observed types: array. Shapes: 1. Count: 8. Max items: 104. | false |
| Groups Items | `result.$json.groups[]` | Parser-detected grouped result array item inside scalar result JSON. | Observed types: object. Shapes: 1. Count: 80. | false |
| Remaining Substantive | `result.$json.remainingSubstantive` | Parser-detected remaining progress count inside scalar result JSON. | Observed types: number. Shapes: 1. Count: 8. | false |
| Repo Abs | `result.$json.repoAbs` | Parser-detected repository path inside scalar result JSON. | Observed types: string. Shapes: 1. Count: 8. Max length: 84. | false |
| Total Substantive | `result.$json.totalSubstantive` | Parser-detected total substantive count inside scalar result JSON. | Observed types: number. Shapes: 1. Count: 8. | false |
| Total Trivial | `result.$json.totalTrivial` | Parser-detected total trivial count inside scalar result JSON. | Observed types: number. Shapes: 1. Count: 8. | false |
| Angles | `result.angles` | Structural array containing search or research angle result items. | Observed types: array. Shapes: 1. Count: 1. Max items: 5. | false |
| Angles Items | `result.angles[]` | Structural item container for angle fields. | Observed types: object. Shapes: 1. Count: 5. | false |
| Label | `result.angles[].label` | Label text for an angle result item. | Observed types: string. Shapes: 1. Count: 5. Max length: 35. | true |
| Query | `result.angles[].query` | Query text for an angle result item. | Observed types: string. Shapes: 1. Count: 5. Max length: 122. | true |
| Rationale | `result.angles[].rationale` | Rationale text for an angle result item. | Observed types: string. Shapes: 1. Count: 5. Max length: 177. | true |
| Batch | `result.batch` | Batch number for a generated result set. | Observed types: number. Shapes: 1. Count: 824. | true |
| Caveats | `result.caveats` | Caveat text returned with a synthesized result. | Observed types: string. Shapes: 1. Count: 1. Max length: 1581. | true |
| Claims | `result.claims` | Structural array containing claim result items. | Observed types: array. Shapes: 2. Count: 20. Max items: 5. | false |
| Claims Items | `result.claims[]` | Structural item container for claim fields. | Observed types: object. Shapes: 1. Count: 85. | false |
| Claim | `result.claims[].claim` | Claim text inside a claim result item. | Observed types: string. Shapes: 1. Count: 85. Max length: 407. | true |
| Importance | `result.claims[].importance` | Importance value inside a claim result item. | Observed types: string. Shapes: 1. Count: 85. Max length: 10. | true |
| Quote | `result.claims[].quote` | Quote text inside a claim result item. | Observed types: string. Shapes: 1. Count: 85. Max length: 317. | true |
| Confidence | `result.confidence` | Confidence value returned with the result. | Observed types: string. Shapes: 2. Count: 75. Max length: 6. | true |
| Counter Source | `result.counterSource` | Counter-source text returned with the result. | Observed types: string. Shapes: 1. Count: 74. Max length: 390. | true |
| Evidence | `result.evidence` | Evidence text returned with the result. | Observed types: string. Shapes: 2. Count: 75. Max length: 1860. | true |
| Findings | `result.findings` | Structural array containing finding result items. | Observed types: array. Shapes: 1. Count: 1. Max items: 13. | false |
| Findings Items | `result.findings[]` | Structural item container for finding fields. | Observed types: object. Shapes: 1. Count: 10. | false |
| Claim | `result.findings[].claim` | Claim text inside a finding result item. | Observed types: string. Shapes: 1. Count: 10. Max length: 450. | true |
| Confidence | `result.findings[].confidence` | Confidence value inside a finding result item. | Observed types: string. Shapes: 1. Count: 10. Max length: 6. | true |
| Evidence | `result.findings[].evidence` | Evidence text inside a finding result item. | Observed types: string. Shapes: 1. Count: 10. Max length: 647. | true |
| Sources | `result.findings[].sources` | Source list inside a finding result item. | Observed types: array. Shapes: 1. Count: 10. Max items: 2. | true |
| Vote | `result.findings[].vote` | Vote value inside a finding result item. | Observed types: string. Shapes: 1. Count: 10. Max length: 59. | true |
| Global Renames | `result.globalRenames` | Structural array containing global rename result items. | Observed types: array. Shapes: 1. Count: 13. Max items: 14. | false |
| Global Renames Items | `result.globalRenames[]` | Structural item container for global rename fields. | Observed types: object. Shapes: 1. Count: 36. | false |
| Doc | `result.globalRenames[].doc` | Document value inside a global rename result item. | Observed types: string. Shapes: 1. Count: 36. Max length: 183. | true |
| Kind | `result.globalRenames[].kind` | Kind value inside a global rename result item. | Observed types: string. Shapes: 1. Count: 36. Max length: 11. | true |
| New | `result.globalRenames[].new` | New value inside a global rename result item. | Observed types: string. Shapes: 1. Count: 36. Max length: 37. | true |
| Old | `result.globalRenames[].old` | Old value inside a global rename result item. | Observed types: string. Shapes: 1. Count: 36. Max length: 3. | true |
| ID | `result.id` | Identifier returned inside a module-like result object. | Observed types: string. Shapes: 2. Count: 18. Max length: 3. | true |
| Issues | `result.issues` | Structural array containing issue result items. | Observed types: array. Shapes: 1. Count: 1. Max items: 8. | false |
| Issues Items | `result.issues[]` | Structural item container for issue fields. | Observed types: object. Shapes: 1. Count: 8. | false |
| Detail | `result.issues[].detail` | Detail text inside an issue result item. | Observed types: string. Shapes: 1. Count: 8. Max length: 666. | true |
| Kind | `result.issues[].kind` | Kind value inside an issue result item. | Observed types: string. Shapes: 1. Count: 8. Max length: 10. | true |
| Module | `result.issues[].module` | Module value inside an issue result item. | Observed types: string. Shapes: 1. Count: 8. Max length: 33. | true |
| Suggestion | `result.issues[].suggestion` | Suggestion text inside an issue result item. | Observed types: string. Shapes: 1. Count: 8. Max length: 253. | true |
| Module Summary | `result.moduleSummary` | Module summary returned inside a module-like result object. | Observed types: string. Shapes: 2. Count: 18. Max length: 745. | true |
| Modules | `result.modules` | Structural array containing module result items. | Observed types: array. Shapes: 1. Count: 640. Max items: 7. | false |
| Modules Items | `result.modules[]` | Structural item container for module fields. | Observed types: object. Shapes: 1. Count: 1670. | false |
| Global Renames | `result.modules[].globalRenames` | Global rename list inside a module result item. | Observed types: array. Shapes: 1. Count: 1670. Max items: 31. | true |
| ID | `result.modules[].id` | Identifier inside a module result item. | Observed types: string. Shapes: 1. Count: 1670. Max length: 3. | true |
| Module Summary | `result.modules[].moduleSummary` | Module summary inside a module result item. | Observed types: string. Shapes: 1. Count: 1670. Max length: 1825. | true |
| New Module Name | `result.modules[].newModuleName` | New module name inside a module result item. | Observed types: string. Shapes: 1. Count: 1670. Max length: 41. | true |
| Rewritten Source | `result.modules[].rewrittenSource` | Rewritten source inside a module result item. | Observed types: string. Shapes: 1. Count: 1670. Max length: 115633. | true |
| New Module Name | `result.newModuleName` | New module name returned inside a module-like result object. | Observed types: string. Shapes: 2. Count: 18. Max length: 30. | true |
| Notes | `result.notes` | Notes returned with the result. | Observed types: string. Shapes: 1. Count: 1. Max length: 1360. | true |
| Open Questions | `result.openQuestions` | Structural array containing open question strings. | Observed types: array. Shapes: 1. Count: 1. Max items: 4. | false |
| Open Questions Items | `result.openQuestions[]` | Open question string returned with the result. | Observed types: string. Shapes: 1. Count: 4. Max length: 261. | true |
| Publish Date | `result.publishDate` | Publish date returned with the result. | Observed types: string. Shapes: 2. Count: 20. Max length: 108. | true |
| Question | `result.question` | Question text returned with the result. | Observed types: string. Shapes: 1. Count: 1. Max length: 656. | true |
| Refuted | `result.refuted` | Refuted flag returned with the result. | Observed types: bool. Shapes: 2. Count: 75. | true |
| Results | `result.results` | Structural array containing result item fields. | Observed types: array. Shapes: 1. Count: 5. Max items: 6. | false |
| Results Items | `result.results[]` | Structural item container for result item fields. | Observed types: object. Shapes: 1. Count: 30. | false |
| Relevance | `result.results[].relevance` | Relevance value inside a result item. | Observed types: string. Shapes: 1. Count: 30. Max length: 6. | true |
| Snippet | `result.results[].snippet` | Snippet text inside a result item. | Observed types: string. Shapes: 1. Count: 30. Max length: 597. | true |
| Title | `result.results[].title` | Title text inside a result item. | Observed types: string. Shapes: 1. Count: 30. Max length: 95. | true |
| URL | `result.results[].url` | URL value inside a result item. | Observed types: string. Shapes: 1. Count: 30. Max length: 129. | true |
| Rewritten Source | `result.rewrittenSource` | Rewritten source returned inside a module-like result object. | Observed types: string. Shapes: 2. Count: 18. Max length: 9633. | true |
| Source Quality | `result.sourceQuality` | Source quality returned with the result. | Observed types: string. Shapes: 2. Count: 20. Max length: 9. | true |
| Summary | `result.summary` | Summary text returned with the result. | Observed types: string. Shapes: 2. Count: 2. Max length: 1658. | true |
| Verdict | `result.verdict` | Verdict value returned with the result. | Observed types: string. Shapes: 1. Count: 1. Max length: 11. | true |
| Written | `result.written` | Written count for a generated result set. | Observed types: number. Shapes: 1. Count: 824. | true |
| Type | `type` | Routes the top-level record to titlebar category badges and metadata views. | Observed types: string. Shapes: 13. Count: 1593. Max length: 6. | false |

## Derived Form Content

| Form Field | Raw Path | Value Source | Rendering |
| --- | --- | --- | --- |
| Result | `result` | Read directly from `result` when present. | Render scalar strings as wrapped text; render objects as a compact keyset with visible child fields below. |
| Label | `result.angles[].label` | For each item in `result.angles`, read `label`. | Render in the Angles nested table as compact text. |
| Query | `result.angles[].query` | For each item in `result.angles`, read `query`. | Render in the Angles nested table as wrapped text. |
| Rationale | `result.angles[].rationale` | For each item in `result.angles`, read `rationale`. | Render in the Angles nested table as wrapped text. |
| Batch | `result.batch` | Read directly from `result.batch` when present. | Render as a compact numeric value. |
| Caveats | `result.caveats` | Read directly from `result.caveats` when present. | Render as complete wrapped long text in a bounded scroll area with preserved line breaks. |
| Claim | `result.claims[].claim` | For each item in `result.claims`, read `claim`. | Render in the Claims nested table as wrapped text. |
| Importance | `result.claims[].importance` | For each item in `result.claims`, read `importance`. | Render in the Claims nested table as a compact scalar. |
| Quote | `result.claims[].quote` | For each item in `result.claims`, read `quote`. | Render in the Claims nested table as quoted wrapped text. |
| Confidence | `result.confidence` | Read directly from `result.confidence` when present. | Render as a compact scalar value. |
| Counter Source | `result.counterSource` | Read directly from `result.counterSource` when present. | Render as wrapped text. |
| Evidence | `result.evidence` | Read directly from `result.evidence` when present. | Render as complete wrapped long text in a bounded scroll area with preserved line breaks. |
| Claim | `result.findings[].claim` | For each item in `result.findings`, read `claim`. | Render in the Findings nested table as wrapped text. |
| Confidence | `result.findings[].confidence` | For each item in `result.findings`, read `confidence`. | Render in the Findings nested table as a compact scalar. |
| Evidence | `result.findings[].evidence` | For each item in `result.findings`, read `evidence`. | Render in the Findings nested table as wrapped text. |
| Sources | `result.findings[].sources` | For each item in `result.findings`, read `sources`. | Render in the Findings nested table as a compact nested list. |
| Vote | `result.findings[].vote` | For each item in `result.findings`, read `vote`. | Render in the Findings nested table as a compact scalar. |
| Doc | `result.globalRenames[].doc` | For each item in `result.globalRenames`, read `doc`. | Render in the Global Renames nested table as wrapped text. |
| Kind | `result.globalRenames[].kind` | For each item in `result.globalRenames`, read `kind`. | Render in the Global Renames nested table as a compact scalar. |
| New | `result.globalRenames[].new` | For each item in `result.globalRenames`, read `new`. | Render in the Global Renames nested table as code-like text. |
| Old | `result.globalRenames[].old` | For each item in `result.globalRenames`, read `old`. | Render in the Global Renames nested table as code-like text. |
| ID | `result.id` | Read directly from `result.id` when present. | Render as a compact copyable identifier. |
| Detail | `result.issues[].detail` | For each item in `result.issues`, read `detail`. | Render in the Issues nested table as wrapped text. |
| Kind | `result.issues[].kind` | For each item in `result.issues`, read `kind`. | Render in the Issues nested table as a compact scalar. |
| Module | `result.issues[].module` | For each item in `result.issues`, read `module`. | Render in the Issues nested table as code-like text. |
| Suggestion | `result.issues[].suggestion` | For each item in `result.issues`, read `suggestion`. | Render in the Issues nested table as wrapped text. |
| Module Summary | `result.moduleSummary` | Read directly from `result.moduleSummary` when present. | Render as complete wrapped long text in a bounded scroll area with preserved line breaks. |
| Global Renames | `result.modules[].globalRenames` | For each item in `result.modules`, read `globalRenames`. | Render in the Modules nested table as a compact nested rename list or keyset. |
| ID | `result.modules[].id` | For each item in `result.modules`, read `id`. | Render in the Modules nested table as a compact copyable identifier. |
| Module Summary | `result.modules[].moduleSummary` | For each item in `result.modules`, read `moduleSummary`. | Render in the Modules nested table as wrapped text. |
| New Module Name | `result.modules[].newModuleName` | For each item in `result.modules`, read `newModuleName`. | Render in the Modules nested table as code-like text. |
| Rewritten Source | `result.modules[].rewrittenSource` | For each item in `result.modules`, read `rewrittenSource`. | Render in the Modules nested table as complete code text in a bounded scroll cell with preserved line breaks. |
| New Module Name | `result.newModuleName` | Read directly from `result.newModuleName` when present. | Render as code-like text. |
| Notes | `result.notes` | Read directly from `result.notes` when present. | Render as complete wrapped long text in a bounded scroll area with preserved line breaks. |
| Open Questions | `result.openQuestions[]` | For each item in `result.openQuestions`, read the string item. | Render as a compact nested list. |
| Publish Date | `result.publishDate` | Read directly from `result.publishDate` when present. | Render as a compact date-like scalar. |
| Question | `result.question` | Read directly from `result.question` when present. | Render as complete wrapped long text in a bounded scroll area with preserved line breaks. |
| Refuted | `result.refuted` | Read directly from `result.refuted` when present. | Render as a compact boolean value. |
| Relevance | `result.results[].relevance` | For each item in `result.results`, read `relevance`. | Render in the Results nested table as a compact scalar. |
| Snippet | `result.results[].snippet` | For each item in `result.results`, read `snippet`. | Render in the Results nested table as wrapped text. |
| Title | `result.results[].title` | For each item in `result.results`, read `title`. | Render in the Results nested table as wrapped text. |
| URL | `result.results[].url` | For each item in `result.results`, read `url`. | Render in the Results nested table as a copyable URL. |
| Rewritten Source | `result.rewrittenSource` | Read directly from `result.rewrittenSource` when present. | Render as complete syntax-highlighted code in a bounded scroll area with preserved line breaks. |
| Source Quality | `result.sourceQuality` | Read directly from `result.sourceQuality` when present. | Render as a compact scalar value. |
| Summary | `result.summary` | Read directly from `result.summary` when present. | Render as complete wrapped long text in a bounded scroll area with preserved line breaks. |
| Verdict | `result.verdict` | Read directly from `result.verdict` when present. | Render as a compact scalar value. |
| Written | `result.written` | Read directly from `result.written` when present. | Render as a compact numeric value. |

## Card Design

```text
+--------------------------------------------------------------------------------+
| [Result] [Raw Event]                                                 [pin] [x] |
+--------------------------------------------------------------------------------+
|                            Content | Metadata | Raw                            |
+--------------------------------------------------------------------------------+
| Result              <result scalar text, or object keyset>                     |
| Batch               <result.batch>                                             |
| Written             <result.written>                                           |
| ID                  <result.id>                                                |
| New Module Name     <result.newModuleName>                                     |
| Source Quality      <result.sourceQuality>                                     |
| Publish Date        <result.publishDate>                                       |
| Confidence          <result.confidence>                                        |
| Refuted             <result.refuted>                                           |
| Verdict             <result.verdict>                                           |
|                                                                                |
| Summary             <result.summary, wrapped in bounded scroll area>           |
| Question            <result.question, wrapped in bounded scroll area>          |
| Caveats             <result.caveats, wrapped in bounded scroll area>           |
| Evidence            <result.evidence, wrapped in bounded scroll area>          |
| Counter Source      <result.counterSource, wrapped>                            |
| Notes               <result.notes, wrapped in bounded scroll area>             |
| Module Summary      <result.moduleSummary, wrapped in bounded scroll area>     |
| Rewritten Source    <result.rewrittenSource, complete scrollable code>         |
|                                                                                |
| Angles                                                                         |
|   | Label | Query | Rationale |                                               |
|   | <label> | <query> | <rationale> |                                         |
|   | ... | ... | ... |                                                        |
|                                                                                |
| Claims                                                                         |
|   | Claim | Importance | Quote |                                             |
|   | <claim> | <importance> | <quote> |                                      |
|   | ... | ... | ... |                                                        |
|                                                                                |
| Findings                                                                       |
|   | Claim | Confidence | Evidence | Sources | Vote |                         |
|   | <claim> | <confidence> | <evidence> | <sources> | <vote> |               |
|   | ... | ... | ... | ... | ... |                                            |
|                                                                                |
| Global Renames                                                                 |
|   | Doc | Kind | Old | New |                                                 |
|   | <doc> | <kind> | <old> | <new> |                                        |
|   | ... | ... | ... | ... |                                                  |
|                                                                                |
| Issues                                                                         |
|   | Module | Kind | Detail | Suggestion |                                    |
|   | <module> | <kind> | <detail> | <suggestion> |                            |
|   | ... | ... | ... | ... |                                                  |
|                                                                                |
| Modules                                                                        |
|   | ID | New Module Name | Module Summary | Rewritten Source | Global Renames |
|   | <id> | <newModuleName> | <moduleSummary> | <code> | <renames> |          |
|   | ... | ... | ... | ... | ... |                                            |
|                                                                                |
| Open Questions                                                                 |
|   - <result.openQuestions[] item>                                              |
|   - ...                                                                        |
|                                                                                |
| Results                                                                        |
|   | Title | URL | Relevance | Snippet |                                      |
|   | <title> | <url> | <relevance> | <snippet> |                              |
|   | ... | ... | ... | ... |                                                  |
+--------------------------------------------------------------------------------+
```
