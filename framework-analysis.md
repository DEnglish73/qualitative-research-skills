# Framework analysis, codebook TA, template analysis

Read this when comparing cases against a structured category set, when more than one person is analyzing, or when a program or policy decision needs a defensible audit trail from data to recommendation.

These three approaches are siblings. All use a structured working framework applied across cases while leaving room for inductive additions. Differences worth knowing:

| Approach | Origin | Distinctive feature |
|---|---|---|
| Framework analysis | Ritchie and Spencer, NatCen; Gale et al. 2013 | Case-by-category matrix as the analytic device |
| Codebook TA | Braun and Clarke's middle variant | Structured codebook, thematic output, less matrix-heavy |
| Template analysis | King | Hierarchical coding template developed on a subset, then applied and revised |

Pick framework analysis when cross-case comparison is the point. Pick template analysis when a hierarchy of codes matters more than the matrix. Pick codebook TA when the audience expects themes but the team needs coding structure.

## Why this family suits applied program work

Reflexive TA assumes a single immersed analyst and treats subjectivity as a resource. Framework analysis assumes several analysts, a deadline, and a decision-maker who will ask which sites or participants said what. The matrix makes that answerable in a way a theme narrative cannot. It is also the easier method to hand off partway through, which matters when the analysis outlives the analyst's availability.

## Procedure

**1. Familiarization.** Read the full corpus. Same standard as any method.

**2. Build the initial working framework.** Draw categories from three sources: the research questions, an existing framework if one was handed to you, and open coding of two or three transcripts chosen for contrast. Categories get names and one-line definitions from the start.

**3. Apply and revise.** Index every transcript against the framework. When data will not fit a category, add or redefine rather than forcing it. Log every framework change with a date and reason; that log is the method's main rigor claim.

**4. Charting.** Build the matrix: rows are cases (participants, sites, cohorts), columns are categories, cells hold **summarized data with turn IDs**, not raw quotes and not interpretation. Summaries stay close to the participant's own words, since abstraction at this stage is unrecoverable later.

```
case_id | role/site | category_A | category_B | category_C | ...
P01     | imaging   | "could not complete SSO, gave up after 10 min (T004)" | ... |
```

**5. Interpretation.** Read the matrix both ways. Down a column for range and pattern within a category. Across a row for the coherence of one case. Cross-case comparison is where this method earns its keep: which cases cluster, which are outliers, and what distinguishes them.

## Multi-analyst work

This is the family where coder comparison is methodologically appropriate, but the aim is calibration, not statistics.

- Two analysts index the same two transcripts independently, then compare and reconcile category definitions. Disagreement usually reveals a fuzzy definition rather than a careless coder.
- Report the process ("framework reconciled across two analysts after independent indexing of 2 of 11 transcripts"), not a kappa, unless the audience explicitly requires reliability statistics. If they do, you are closer to content analysis and should say so.
- One person owns the framework version. Uncontrolled parallel edits produce silent divergence.

## Output template

```markdown
# Framework analysis: [source, date]

## Method note
[per SKILL.md template, naming framework analysis and the framework's origin]

## Working framework
| Category | Definition | Origin (a priori / inductive) | Added or revised |
|---|---|---|---|

## Matrix
[full case-by-category chart, or a pointer to the CSV if large]

## Cross-case findings
### [Finding stated as a claim]
Pattern: [what the matrix shows, with cases named or coded]
Range: [the spread, including cases that do not fit]
Evidence: "[verbatim]" — [attribution] (T042)
Cases without this: [which, and any distinguishing feature]

## Framework change log
| Date | Change | Reason |
```

## Traps

- **Matrix cells holding interpretation.** Once a cell says "frustrated with access" instead of what the participant said, the audit trail is broken and no one can check the reading.
- **Forcing data into categories** to keep the framework tidy. The unfitting data is the signal.
- **Treating the matrix as the finding.** A chart is not analysis. The claims come from reading it.
- **Reporting agreement statistics as the rigor claim** while describing the work as framework analysis. State the reconciliation process instead.
- **Empty columns left unremarked.** A category nobody spoke to is informative and should be reported, not deleted.
