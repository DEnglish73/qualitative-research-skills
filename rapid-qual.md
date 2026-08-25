# Rapid qualitative analysis

Read this when a decision lands before a full analysis can be done: a steering committee in four days, a sprint planning session tomorrow, a funder call this week.

Rapid analysis is a legitimate method with its own literature (RAP, rapid assessment procedures, and the rapid qualitative analysis approaches used in implementation science). It is not a shortcut pretending to be thematic analysis. The discipline is labeling it accurately and being specific about what was given up.

## When to use it, and when to refuse

Use it when the decision date is fixed and earlier than a full analysis allows, and when the question is practical (what is blocking people, what should we fix first).

Do not use it when:

- The output will be published or presented as a study. Rapid analysis will not survive peer review as thematic analysis, and relabeling it later is worse than doing it properly now.
- The question is interpretive or theoretical. Speed and latent-level work do not combine.
- The stakes make a wrong read expensive and a fuller analysis is possible with modest delay. Offer the delay explicitly; users often have more room than the initial ask suggests.

Say plainly which of these applies. A user with a real deadline is better served by an honest rapid analysis than by a slow analysis that arrives late.

## Procedure

**1. Set the domains before reading.** Four to eight domains drawn from the decision at hand, not from the data. For a product session: access and onboarding, fit with workflow, data compatibility, output trust, unmet needs, comparison to alternatives. Domains are containers, and they are what makes this method quick.

**2. Build a summary template.** One template per source, with the same domains in the same order every time. Consistency across sources is what makes the roll-up possible.

**3. Fill one template per transcript.** Per domain: a short summary in the participant's terms, plus two or three verbatim quotes with turn IDs. Keep the turn IDs, since they are the only thing that makes the output checkable later, and they cost nothing at the time.

**4. Roll up into a matrix.** Domains as rows, sources or participants as columns. Read across for convergence, down for the range within a domain.

**5. Write the findings.** Per domain: what was heard, how many distinct speakers, what needs a decision. Keep the domain structure visible rather than dressing the output up as themes.

## Output template

```markdown
# Rapid qualitative analysis: [source, date]

## Method note
Rapid qualitative analysis (domain summary templates and matrix roll-up). This is not thematic analysis.
Domains were set a priori from [decision context].
What was given up: no line-by-line coding, no latent interpretation, no theme construction, limited attention to disconfirming data.
Corpus: [sources, N speakers, internal vs external].
Turnaround: [dates].
Confidence: [where the read is solid, where it is provisional]

## Domain findings
### [Domain]
Heard from: [N of M distinct speakers]
Summary: [3 to 5 lines in participants' terms]
Quotes:
- "[verbatim]" — [attribution] (T042)
Decision needed: [what, by whom, or "none"]
Confidence: [high / provisional, with why]

## Matrix
[domains by participants]

## What a full analysis would likely add
[Honest assessment: which domains looked like they had more underneath, what a fuller read would test]
```

## Upgrading later

Rapid analysis done with turn IDs and preserved templates can be extended into a full analysis without redoing the prep. If that is plausible, keep `codes.csv` populated as you go, though rapid analysis does not require it. The marginal cost is small and it preserves the option.

Note in the delivery that the rapid findings were domain-driven, so a later inductive analysis may produce a different structure. That is expected, not a contradiction to be explained away.

## Traps

- **Calling it thematic analysis.** The most damaging move available, since it invites methodological questions the output cannot answer.
- **Domains that are too many or too fine.** Above eight, the speed advantage disappears.
- **Dropping quotes to save time.** Quotes are what make the output usable in a deck, and gathering them later means re-reading the corpus.
- **Presenting provisional reads with the same confidence as solid ones.** The confidence field exists so a decision-maker can weigh them differently.
- **Skipping the disconfirming check entirely.** Even under deadline, one pass looking for data that contradicts each domain summary is worth the twenty minutes.
